
# 01 - JSON schema (Schema)

`ogc.bbr.tutorial.exercise1` *v0.1*

Provide and validate an example JSON file.  Shows how the examples management component works and introduces a basic JSON schema.  (Note that building blocks may documented other forms of specification, however JSON schemas support semantic interoperability using available standard approaches and OpenAPI applications, and will be featured in these tutorials.)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 1

Goal: take a simple JSON schema and test with an example

An example of the end result is available [here](/bblock/ogc.bbr.tutorial.exercise1_completed)

### Steps
- un-comment the reference to a local file in [examples.yaml](examples.yaml)
- run build
- run viewer
- navigate to [Exercise 1]((/bblock/ogc.bbr.tutorial.exercise1)
- navigate to [Examples]((/bblock/ogc.bbr.tutorial.exercise1/examples) tab
- view validation results at [build-local/...](/register/build-local/tests/report.html#bblock-ogc.bbr.tutorial.exercise1)
## Examples

### Reference a local file for examples
[Example from Exercise  1](/bblock/ogc.bbr.tutorial.exercise1/example)

In **Markdown** format.
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

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise1/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise1/schema.yaml)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise1`

