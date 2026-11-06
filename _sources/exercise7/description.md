## Exercise 7 - Importing and profiling from an external register

Importing from another Building Block register allows grouping of related Building Blocks into single governance environments using GIT.

This forces **transparency of reuse**, i.e. FAIR principles. 

It also means maintenance is relatively simple for static Building Blocks - such as those defining published standards.

### Imported rules need a closure

Profiling a block imports its **rules** as well as its schema. The `topo-line` block from the
[topo-feature](https://ogcincubator.github.io/topo-feature) register carries a SHACL rule
(`topo-refs-exist`) requiring every feature a topology references to be **present in the graph being
validated, with a Point geometry**. The example line references points `P1` and `P2` by id, but - like
most minimal examples - does not define them, so the imported rule fails.

A **SHACL closure** fixes this. It is a Turtle file of background data that is merged into the example's
RDF graph before SHACL validation runs, without becoming part of the example itself.
[closure.ttl](closure.ttl) supplies `P1` and `P2` as minimal stubs that carry only what the imported rules
check: a Point geometry with coordinates.

The closure's IRIs must match the IRIs the example's ids become after semantic uplift. The example in
[examples.yaml](examples.yaml) therefore sets `base-uri`, which the relative ids `"P1"` and `"P2"` resolve
against.

A closure can be declared for a single example snippet (`shacl-closure` in `examples.yaml`, used here), or
for every example and test of the block (`shaclClosures` in `bblock.json`). Declare each closure in one
place only: closures are merged across all blocks that depend on each other, and parsing the same file
more than once can produce spurious validation failures.

### Steps
- review the docs on [imports](https://ogcincubator.github.io/bblocks-docs/create/imports)
- view the import in line 17 of [bblocks-config.yaml](../../bblocks-config.yaml)
- uncomment the reference to `topo-line` in [schema.yaml](schema.yaml)
- build and view
- examine the examples and validation reports: the example fails the imported `topo-refs-exist` rule
  because `P1` and `P2` are not in the graph
- examine [closure.ttl](closure.ttl), and the `base-uri` in [examples.yaml](examples.yaml) its IRIs match
- in [examples.yaml](examples.yaml), uncomment the `shacl-closure` entry under the snippet so that it
  references `closure.ttl`
- build and view
- examine the validation reports again: the example now passes, while the test in [tests](tests) - a line
  with three points - still fails as expected, on the JSON schema `maxItems: 2` constraint of this profile
