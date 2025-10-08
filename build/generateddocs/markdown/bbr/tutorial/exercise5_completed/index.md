
# 05 - Features (completed) (Schema)

`ogc.bbr.tutorial.exercise5_completed` *v1.0*

This example shows a simple customisation for OGC API Feature schemas

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Using a standard container

This is an **interoperable** approach to packaging a data model in a standardised structure.

i.e. the attributes (properties) are managed independently of the packaging container (Feature) 

In this case we use the schema from the previous examples.

This building block **inherits** reusable semantic annotations from a common library, simplifying implementation.

### Steps
- uncomment the reference to the previous exercise schema in schema.yaml
- run build, view etc
- examine "Semantic Uplift" and note that event though no `context.jsonld` is present the building block inherits and combines the two building blocks semantic annotations.




## Examples

### GeoJSON - specialisation example.
This examples shows how to define a customised schema based on an existing building block - in this case the *OGC API Features* basic GeoJSON Feature response
#### json
```json
{
  "@context": {
    "mynamespace": "http://example.org/ns1/"
  },
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862874
      ]
    ]
  },
  "properties": {
    "a": "mynamespace:aThing",
    "b": 23,
    "c": 0.1
  }
}

```

#### yaml
```yaml
id: 16
type: Feature
geometry: null
properties:
  a: mynamespace:aThing
  b: 23
  c: 0.1

```

#### jsonld
```jsonld
{
  "@context": [
    {
      "mynamespace": "http://example.com/mythings/"
    },
    "https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise5_completed/context.jsonld",
    {
      "mynamespace": "http://example.org/ns1/"
    }
  ],
  "id": "f1",
  "type": "Feature",
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -111.67183507997295,
        40.056709946862874
      ],
      [
        -111.71,
        40.156709946862875
      ]
    ]
  },
  "properties": {
    "a": "mynamespace:aThing",
    "b": 23,
    "c": 0.1
  }
}
```

#### ttl
```ttl
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://example.com/features/f1> a geojson:Feature ;
    geojson:geometry [ a geojson:LineString ;
            geojson:coordinates ( ( -1.116718e+02 4.005671e+01 ) ( -1.1171e+02 4.015671e+01 ) ) ] .


```

## Schema

```yaml
$schema: https://raw.githubusercontent.com/opengeospatial/bblocks-postprocess/refs/heads/master/ogc/bblocks/schemas/examples.schema.yaml
description: Example of a simple GeoJSON Feature specialisation
allOf:
- $ref: https://opengeospatial.github.io/bblocks/annotated-schemas/geo/features/feature/schema.yaml
- properties:
    properties:
      $ref: https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise4/schema.yaml

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise5_completed/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise5_completed/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "Feature": "geojson:Feature",
    "FeatureCollection": "geojson:FeatureCollection",
    "GeometryCollection": "geojson:GeometryCollection",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "features": {
      "@container": "@set",
      "@id": "geojson:features"
    },
    "type": "@type",
    "id": "@id",
    "properties": "@nest",
    "geometry": {
      "@context": {
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      },
      "@id": "geojson:geometry"
    },
    "bbox": {
      "@container": "@list",
      "@id": "geojson:bbox"
    },
    "links": {
      "@context": {
        "href": {
          "@type": "@id",
          "@id": "oa:hasTarget"
        },
        "rel": {
          "@context": {
            "@base": "http://www.iana.org/assignments/relation/"
          },
          "@id": "http://www.iana.org/assignments/relation",
          "@type": "@id"
        },
        "type": "dct:type",
        "hreflang": "dct:language",
        "title": "rdfs:label",
        "length": "dct:extent"
      },
      "@id": "rdfs:seeAlso"
    },
    "geojson": "https://purl.org/geojson/vocab#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "oa": "http://www.w3.org/ns/oa#",
    "dct": "http://purl.org/dc/terms/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-tutorial/build/annotated/bbr/tutorial/exercise5_completed/context.jsonld)

## Sources

* [OGC API - Features, Part 1, 7.16.2: Feature Response](https://docs.ogc.org/is/17-069r3/17-069r3.html#_response_7)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise5_completed`

