
# 01 - JSON schema (completed) (Schema)

`ogc.bbr.tutorial.exercise1_completed` *v0.1*

Shows what Exercise 1 looks like when finished

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 1

Goal: take a simple JSON schema and test with an example

### Steps
- un-comment the reference to a local file in [examples.yaml](examples.yaml)
- run build
- run viewer
- navigate to [Exercise 1](/bblock/ogc.bbr.tutorial.exercise1_completed)
- view validation results at [build-local/...](/register/build-local/tests/report.html#bblock-ogc.bbr.tutorial.exercise1_completed)
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

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise1_completed/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise1_completed/schema.yaml)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise1_completed`

