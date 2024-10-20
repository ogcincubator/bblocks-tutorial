
# Exercise 4 (Model)

`ogc.bbr.template.exercise4` *v0.1*

Profile with rules

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 3

Goal: Profile a building block with additional rules, with tests

Note this illustrates how to use examples to test rules fail when expected. This is a critical capability for complex systems.

### Steps
- uncomment import from schema.yaml
- run build
- run viewer
- navigate to "Exercise 4"/Validation
- view validation results at [Validation Report](validation) or [build-local/...](/register/build-local/tests/bbr/template/exercise3/_report.json)
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/ogcincubator/bblocks-tutorial/undefined/build/annotated/bbr/template/exercise4/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/ogcincubator/bblocks-tutorial/undefined/build/annotated/bbr/template/exercise4/schema.yaml)

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise4`
