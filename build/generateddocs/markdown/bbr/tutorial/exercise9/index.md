
# 09 - RDF BB (Model)

`ogc.bbr.tutorial.exercise9` *v0.1*

A building block defining a building block for a data model described in ontology standards OWL and SHACL.  Such a building block allows logical constraints to be inherited by multiple implementation schemas using semantic annotations (such as JSON-LD)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Exercise 9

Goal: Define a Building Block for a semantic data model using OWL and SHACL

This supports **transparent dependency relationships** between modules of an model composed of multiple ontologies.

It also support CI/CT of SHACL rules including testing against _pass_ and _fail_ tests, as per [Excercise 4](../exercise4_completed) - this is extremely important since SHACL rules are hard to debug.

Note also this approach is appropriate where a given schema is **one of many possible schemas** for the same underlying semantic model, and allows defining the model and logical constraints independently, with re-usable validation rules and unit testing advantages.

**A richer integration with the PyLODE documentation tool is planned to support generation of comprehensive documentation**

### Steps
- uncomment line 12 of [bblock.json](bblock.json) to identify the source 
- examine file [ontology.ttl-example](ontology.ttl-example)"
- rename to **ontology.ttl**
- run build
- run viewer
- navigate to "Exercise 9"/Ontology and examine `Classes` and `Properties`
- view validation results on "About
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
* Path: `_sources/exercise9`

