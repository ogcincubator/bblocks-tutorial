## Exercise 7 - Importing and profiling from an external register

### Imported rules need a closure

The `topo-line` block imported from the [topo-feature](https://ogcincubator.github.io/topo-feature)
register carries a SHACL rule (`topo-refs-exist`) requiring every feature a topology references to be
present in the graph being validated, with a Point geometry. The example references points `P1` and `P2`
without defining them, so [closure.ttl](closure.ttl) supplies minimal Point stubs as a **SHACL closure**:
background data merged into the example's RDF graph before validation. The example's `base-uri` in [examples.yaml](examples.yaml) makes the
ids resolve to the same IRIs the closure uses.

### Steps
- view the import in line 17 of [bblocks-config.yaml](../../bblocks-config.yaml)
- uncomment the reference to `topo-line` in [schema.yaml](schema.yaml)
- reference [closure.ttl](closure.ttl) from the example snippet's `shacl-closure` list in
  [examples.yaml](examples.yaml)
- examine the examples and validation reports.
