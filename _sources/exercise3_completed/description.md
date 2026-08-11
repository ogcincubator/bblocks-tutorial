## Exercise 3

Goal: Redeclare (override) a JSON-LD binding inherited from another block

A block whose schema composes another via `allOf`/`$ref` — as this exercise does with
[Exercise 2 (completed)](../exercise2_completed) — can redeclare a term's mapping in its own `context.jsonld`
and have it win over the inherited one. This is useful for a profile that needs to specialise an inherited term
without forking the base schema or context.

This exercise's [schema.yaml](schema.yaml) composes Exercise 2 (completed)'s schema via `allOf`/`$ref` and adds
no new properties of its own — it just redeclares `b`, and [context.jsonld](context.jsonld) overrides its
mapping. It depends on the *completed* Exercise 2 rather than plain Exercise 2 so this reference block is
self-sufficient regardless of your progress on Exercise 2 itself.

### Steps
- navigate to [Semantic Uplift](bblocks://ogc.bbr.tutorial.exercise3_completed/semantic-uplift) tab and compare
  the assembled context here to [Exercise 2 (completed)](../exercise2_completed)'s: `b` resolves to this block's
  own mapping, not Exercise 2's, while `a` and `c` are still inherited unchanged
- choose "RDF/Turtle" on the [Examples](bblocks://ogc.bbr.tutorial.exercise3_completed/examples) tab to see the
  effect on an actual instance

### Why this works

Each block is annotated from its own context in isolation, then the final context is assembled by walking the
compiled schema's `allOf` branches in order — Exercise 2 (completed)'s branch first, this block's own branch
last — so for a property mapped on both sides, the *later* branch wins.

**There's no opt-in for this** — redeclaring a term overrides it whether you meant to or not. See
[Overriding an inherited binding](https://ogcincubator.github.io/bblocks-docs/create/semantic-uplift#overriding-an-inherited-binding)
in the OGC Blocks docs for the full mechanism, including a nuance this exercise doesn't show: Exercise 2 never
sets `@type` on `b`, so there's nothing here to inherit alongside the overridden `@id`. For a worked example that
does show a partial override (only `@id` redeclared, `@type` still inherited) alongside a full one, see the
[`base`](https://ogcincubator.github.io/bblocks-viewer/#/bblock/ogc.bbr.examples.semantic-uplift.override-binding.base?register=https://ogcincubator.github.io/bblocks-examples/build/register.json)/[`child`](https://ogcincubator.github.io/bblocks-viewer/#/bblock/ogc.bbr.examples.semantic-uplift.override-binding.child?register=https://ogcincubator.github.io/bblocks-examples/build/register.json)
pair in `bblocks-examples`.
