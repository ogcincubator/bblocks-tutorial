
# 03 - Override a JSON-LD Binding (completed) (Schema)

`ogc.bbr.tutorial.exercise3_completed` *v0.1*

Profile a block and redeclare one of its inherited JSON-LD bindings so your own mapping wins

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

#### jsonld
```jsonld
{
  "@context": "https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3_completed/context.jsonld",
  "a": "https://example.com/my-a-value",
  "b": 42,
  "c": 7
}
```

#### ttl
```ttl
@prefix ns1: <https://example.org/my-bb-model/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] a <https://example.com/my-a-value> ;
    ns1:c 7 ;
    ns1:more-specific-b 42 .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Profile of Exercise 2 that overrides its inherited "b" binding
allOf:
- $ref: https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise2_completed/schema.yaml
- type: object
  properties:
    b:
      type: number
      x-jsonld-id: https://example.org/my-bb-model/more-specific-b

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3_completed/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3_completed/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "a": "@type",
    "b": "https://example.org/my-bb-model/more-specific-b",
    "c": "https://example.org/my-bb-model/c",
    "mynamespace": "http://example.com/mythings/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3_completed/context.jsonld)

## Sources

* [OGC Blocks docs: Overriding an inherited binding](https://ogcincubator.github.io/bblocks-docs/create/semantic-uplift#overriding-an-inherited-binding)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise3_completed`

