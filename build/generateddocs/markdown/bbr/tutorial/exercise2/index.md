
# 02 - Add a JSON-LD context (Schema)

`ogc.bbr.tutorial.exercise2` *v0.1*

Semantically annotate a schema by adding a simple JSON-LD context

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 2

Goal: Semantically annotate a JSON schema

### Steps
- rename [context.example](context.example) to [context.jsonld](context.jsonld)
- run build
- run viewer
- navigate to "Exercise 2"/Examples
- choose "RDF/Turtle" to see generated RDF
- view "semantic uplift" 
- view validation results at [build-local/...](/register/build-local/tests/bbr/template/exercise2/_report.json)
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

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: My example schema
type: object
properties:
  a:
    type: string
    format: uri
  b:
    type: number
  c:
    type: number
required:
- a
- b

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise2/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise2/schema.yaml)

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise2`

