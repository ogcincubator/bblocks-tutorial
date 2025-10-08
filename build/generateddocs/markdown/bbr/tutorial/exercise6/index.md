
# 06 - Import/Extend (Schema)

`ogc.bbr.tutorial.exercise6` *v1.0*

Profiling a BBlock from another register

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Importing and profiling from an external register

Importing from another Building Block register allows grouping of related Building Blocks into single governance environments using GIT.

This forces **transparency of reuse**, i.e. FAIR principles. 

It also means maintenance is relatively simple for static Building Blocks - such as those defining published standards.


### Steps
- review the docs on [imports](https://ogcincubator.github.io/bblocks-docs/create/imports)
- view the import in line 17 of [bblocks-config.yaml](../../bblocks-config.yaml)
- uncomment the reference to `topo-line` in [schema.yaml](schema.yaml)
- build and view
- examine the examples and validation reports.



## Examples

### Line with 2 points
#### json
```json
{
  "type": "Feature",
  "id": "LineP1P2",
  "geometry": null,
  "topology": {
    "type": "LineString",
    "references": [
      "P1",
      "P2"
    ]
  },
  "properties": null
}
```

## Schema

```yaml
description: Line with only two points
allOf:
- properties:
    topology:
      properties:
        references:
          minItems: 2
          maxItems: 2

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise6/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise6/schema.yaml)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise6`

