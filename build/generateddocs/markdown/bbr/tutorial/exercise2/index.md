
# 02 - JSON-LD (Schema)

`ogc.bbr.tutorial.exercise2` *v0.1*

Semantically annotate a schema by adding a simple JSON-LD context

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 2

Goal: Semantically annotate a JSON schema

[JSON-LD](https://json-ld.org/) **maps JSON data structures to URI**s - which in turn can reference semantic descriptions of those elements.

(It can also map content to URIs - taking keywords and turning them into Linked Data)

The challenge is that these mappings become exponentially harder to build and test as the JSON structure deepens - and common structures may be mapped different ways to different descriptions - unless **FAIR JSON-LD mappings** are created, and **tooling simplifies the complexity**.

Enter the OGC Building Blocks!  The (only, currently) tool that will combine simple schemas and JSON-LD contexts into an application-ready bundle!

### Steps
- rename [context.example](context.example) to [context.jsonld](context.jsonld)
- run build
- run viewer
- navigate to [Examples](/bblock/ogc.bbr.tutorial.exercise2/examples) tab
- choose "RDF/Turtle" to see generated RDF
- navigate to [Semantic Uplift](/bblock/ogc.bbr.tutorial.exercise2/semantic-uplift) tab (present in completed example)
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

