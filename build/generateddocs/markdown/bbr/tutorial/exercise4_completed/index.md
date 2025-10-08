
# 04 - Profiling (completed) (Model)

`ogc.bbr.tutorial.exercise4_completed` *v0.1*

Profile another Building Block with additional constraint rules, include unit testing of these rules with pass and fail cases.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 4

Goal: Profile a building block with additional rules, with tests

Note this illustrates how to use examples to test rules fail when expected. This is a critical capability for complex systems.

### Steps
- uncomment import from schema.yaml
- uncomment line #11 in rules.shacl and examine the additional profile constraint (B<5))
- run build
- run viewer
- navigate to "Exercise 4"/Validation
- view validation results on "about tab"
- move `examples/*-fail` to `tests`
- run build
- run viewer
- view validation results at [Validation Report](validation) or [build-local/...](/register/build-local/tests/bbr/template/exercise3/_report.json)
## Examples

### Valid under new rule
#### json
```json
{
  "a": "mynamespace:aThing",
  "b": 6,
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
    "https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise4_completed/context.jsonld"
  ],
  "a": "mynamespace:aThing",
  "b": 6,
  "c": 1
}
```

#### ttl
```ttl
@prefix mynamespace: <http://example.org/ns1/> .
@prefix ns1: <https://example.org/my-bb-model/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] a mynamespace:aThing ;
    ns1:b 6 ;
    ns1:c 1 .


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
$ref: https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise3/schema.yaml

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise4_completed/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise4_completed/schema.yaml)


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
[context.jsonld](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise4_completed/context.jsonld)

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise4_completed`

