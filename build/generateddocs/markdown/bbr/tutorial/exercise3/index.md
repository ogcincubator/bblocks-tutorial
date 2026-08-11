
# 03 - Override a JSON-LD Binding (Schema)

`ogc.bbr.tutorial.exercise3` *v0.1*

Profile a block and redeclare one of its inherited JSON-LD bindings so your own mapping wins

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 3

Goal: Redeclare (override) a JSON-LD binding inherited from another block

A block whose schema composes another via `allOf`/`$ref` — as this exercise does with [Exercise 2](../exercise2)
— can redeclare a term's mapping in its own `context.jsonld` and have it win over the inherited one. This is
useful for a profile that needs to specialise an inherited term without forking the base schema or context.

This exercise's [schema.yaml](schema.yaml) already composes Exercise 2's schema via `allOf`/`$ref` and adds no
new properties of its own — it just redeclares `b`, ready for its context to override the mapping. As with the
earlier exercises that build on one another, this only shows the full picture once Exercise 2 itself has had its
own `context.jsonld` rename step done too — if you skipped ahead, go back and finish Exercise 2 first.

### Steps
- rename [context.example](context.example) to [context.jsonld](context.jsonld) — it redeclares `b`, which
  [Exercise 2](../exercise2)'s own context already maps to `https://example.org/my-bb-model/b`
- run build
- run viewer
- navigate to [Semantic Uplift](bblocks://ogc.bbr.tutorial.exercise3/semantic-uplift) tab and compare the
  assembled context here to [Exercise 2](../exercise2)'s: `b` should now resolve to this block's own mapping,
  not Exercise 2's, while `a` and `c` are still inherited unchanged
- choose "RDF/Turtle" on the [Examples](bblocks://ogc.bbr.tutorial.exercise3/examples) tab to see the effect on
  an actual instance

### Why this works

Each block is annotated from its own context in isolation, then the final context is assembled by walking the
compiled schema's `allOf` branches in order — Exercise 2's branch first, this block's own branch last — so for a
property mapped on both sides, the *later* branch wins.

**There's no opt-in for this** — redeclaring a term overrides it whether you meant to or not. See
[Overriding an inherited binding](https://ogcincubator.github.io/bblocks-docs/create/semantic-uplift#overriding-an-inherited-binding)
in the OGC Blocks docs for the full mechanism, including a nuance this exercise doesn't show: Exercise 2 never
sets `@type` on `b`, so there's nothing here to inherit alongside the overridden `@id`. For a worked example that
does show a partial override (only `@id` redeclared, `@type` still inherited) alongside a full one, see the
[`base`](https://ogcincubator.github.io/bblocks-viewer/#/bblock/ogc.bbr.examples.semantic-uplift.override-binding.base?register=https://ogcincubator.github.io/bblocks-examples/build/register.json)/[`child`](https://ogcincubator.github.io/bblocks-viewer/#/bblock/ogc.bbr.examples.semantic-uplift.override-binding.child?register=https://ogcincubator.github.io/bblocks-examples/build/register.json)
pair in `bblocks-examples`.

## Examples

### Example instance
#### json
```json
{
  "a": "https://example.com/my-a-value",
  "b": 42,
  "c": 7
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Profile of Exercise 2 that overrides its inherited "b" binding
allOf:
- $ref: https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise2/schema.yaml
- type: object
  properties:
    b:
      type: number

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3/schema.yaml)

## Sources

* [OGC Blocks docs: Overriding an inherited binding](https://ogcincubator.github.io/bblocks-docs/create/semantic-uplift#overriding-an-inherited-binding)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise3`

