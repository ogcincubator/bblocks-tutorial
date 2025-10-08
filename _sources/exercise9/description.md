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