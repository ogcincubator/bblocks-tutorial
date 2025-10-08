
# 09 - RDF BB (completed)  (Model)

`ogc.bbr.tutorial.exercise9_completed` *v0.1*

A building block defining a building block for a data model described in ontology standards OWL and SHACL.  Such a building block allows logical constraints to be inherited by multiple implementation schemas using semantic annotations (such as JSON-LD)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 9

Goal: Define a Building Block for a semantic data model

This approach is appropriate where a given schema is one of many possible schemas for the same underlying semantic model, and allows defining the model and logical constraints independently, with re-usable validation rules and unit testing advantages.

### Steps
- uncomment line
- examine file "ontology.ttl"
- run build
- run viewer
- navigate to "Exercise 9"/Ontology and examine classes
- view validation results on "about tab"
- view validation results at [Validation Report](validation) or [build-local/...](/register/build-local/tests/bbr/template/exercise3/_report.json)
## Examples

### Example
#### ttl
```ttl
@prefix rdf:  <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix :     <https://w3id.org/example#> .
@prefix eg:   <https://w3id.org/example-data#> .

eg:Fred
    a          :Researcher ;
    :partOf    eg:GnomesInc ;
    rdfs:label "Fred the Gardener" .

eg:GnomesInc
    a          :Organization ;
    rdfs:label "Gnomes Inc. Gardeners to the Stars" .
```

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise9_completed`

