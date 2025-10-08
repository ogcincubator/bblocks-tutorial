
# 04 - Profile a BB (using rules) (Model)

`ogc.bbr.tutorial.exercise4` *v0.1*

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
    {}
  ],
  "a": "mynamespace:aThing",
  "b": 6,
  "c": 1
}
```

#### ttl
```ttl


```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise4/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise4/schema.yaml)

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise4`

