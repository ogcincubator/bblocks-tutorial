
# 10 - Profiling an Ontology (Model)

`ogc.bbr.tutorial.exercise10` *v0.1*

Often data models and schemas are re-used with specific constraints - i.e. as a profile. This example shows how using building blocks allows inheritance of rules from a base ontology and addition of such constraints using SHACL.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 10

Goal: Profile a BB by adding additional SHACL Rules

Inheritance of simple, unit-tested SHACL rules is a powerful convenience of the Building Blocks framework. 

### Steps
- run build
- run viewer
- navigate to [validation](validation) tab and see inheritance of rules from Exercise 9
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
    :partOf    eg:GnomesInc, eg:GardenersUnited ;
    rdfs:label "Fred the Gardener" .

eg:GnomesInc
    a          :Organization ;
    rdfs:label "Gnomes Inc. Gardeners to the Stars" .

eg:GardenersUnited
    a          :Organization , :Association ;
    rdfs:label "United Scientific Gardeners Association" .
```

## Sources

* [Sample source document](https://example.com/sources/1)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-tutorial](https://github.com/ogcincubator/bblocks-tutorial)
* Path: `_sources/exercise10`

