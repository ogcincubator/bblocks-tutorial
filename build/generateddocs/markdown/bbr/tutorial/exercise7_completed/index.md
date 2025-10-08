
# 07 - Transforms (completed) (Schema)

`ogc.bbr.tutorial.exercise7_completed` *v0.1*

schema and graph transforms

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 7

Goal: Examine [transform support](https://ogcincubator.github.io/bblocks-docs/create/transforms)

Note: User Experience for FAIR transform publishing is a work in progress - feel free to [contribute](https://github.com/ogcincubator/bblocks-tutorial/issues) ideas!

### Steps
- See the documentation on [transform support](https://ogcincubator.github.io/bblocks-docs/create/transforms)
- rename [transforms.example](context.example) to [transforms.yaml](context.jsonld)
- run build
- run viewer
- navigate to [Transforms](/bblock/ogc.bbr.tutorial.exercise7_completed/transforms) Tab
- examine transforms available
- note how each transform supports specific input formats - e.g. an XSLT transform will be applied to XML
- navigate to [Examples](/bblock/ogc.bbr.tutorial.exercise7_completed/examples) Tab
- click on `Transform Results` button
- Select the transform (drop down list) and view results

### further development

In future there is expected to be a finer-grained binding of transforms to input and output profiles for data conformance, and integrated validation.

Also a "plug-in" custom transform capability 

## Examples

### Example for transforms
#### json
```json
{
  "one": 1,
  "two": 2,
  "string": "value"
}
```

#### jsonld
```jsonld
{
  "@context": "https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise7_completed/context.jsonld",
  "one": 1,
  "two": 2,
  "string": "value"
}
```

#### ttl
```ttl
@prefix ex: <http://example.com/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] ex:hasOne 1 ;
    ex:hasString "value" ;
    ex:hasTwo 2 .


```

## Schema

```yaml
type: object
properties:
  one:
    type: number
    x-jsonld-id: http://example.com/hasOne
  two:
    type: number
    x-jsonld-id: http://example.com/hasTwo
  string:
    type: string
    x-jsonld-id: http://example.com/hasString
x-jsonld-prefixes:
  ex: http://example.com/

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise7_completed/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise7_completed/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "one": "ex:hasOne",
    "two": "ex:hasTwo",
    "string": "ex:hasString",
    "ex": "http://example.com/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise7_completed/context.jsonld)


# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise7_completed`

