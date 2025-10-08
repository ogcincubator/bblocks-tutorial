
# 03 - Add Semantic Rules (Model)

`ogc.bbr.tutorial.exercise3` *v0.1*

Add logical rules using SHACL to exploit semantic annotations

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 3

Goal: Define logical rules to exploit semantic annotation

This will be a basic example that uses the JSON-LD bindings and simple rules.  Note that richer rules can be defined that use referenced semantic models and advanced reasoning, however significant extra functionality is provided simply by being able to identify and operate on schema elements with richer logic languages like SHACL.

### Steps
- uncomment line 11 in [rules.shacl](rules.shacl) 
- run build
- run viewer
- navigate to "Exercise 3"/Validation
- view validation results on "about tab" 

## Examples

### Reference a local file for examples
[Example from Exercise  1](/bblock/ogc.bbr.tutorial.exercise1/example)

In **Markdown** format.
#### json
```json
{
  "a": "mynamespace:aThing",
  "b": 23,
  "c": 1
}


```

#### jsonld
```jsonld
{
  "@context": [
    {
      "mynamespace": "http://example.org/ns1/"
    },
    "https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3/context.jsonld"
  ],
  "a": "mynamespace:aThing",
  "b": 23,
  "c": 1
}
```

#### ttl
```ttl
@prefix mynamespace: <http://example.org/ns1/> .
@prefix ns1: <https://example.org/my-bb-model/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] a mynamespace:aThing ;
    ns1:b 23 ;
    ns1:c 1 .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: My example schema
type: object
properties:
  a:
    type: string
    format: uri
    x-jsonld-id: '@type'
  b:
    type: number
    x-jsonld-id: https://example.org/my-bb-model/b
  c:
    type: number
    x-jsonld-id: https://example.org/my-bb-model/c
required:
- a
- b
x-jsonld-prefixes:
  mynamespace: http://example.org/ns1/

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "a": "@type",
    "b": "https://example.org/my-bb-model/b",
    "c": "https://example.org/my-bb-model/c",
    "mynamespace": "http://example.org/ns1/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3/context.jsonld)

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise3`

