## Exercise 10

Goal: Define a Building Block for a semantic data model using OWL and SHACL

This supports **transparent dependency relationships** between modules of a model composed of multiple ontologies.

It also support CI/CT of SHACL rules including testing against _pass_ and _fail_ tests, as per [Exercise 5](bblocks://ogc.bbr.tutorial.exercise5_completed) - this is extremely important since SHACL rules are hard to debug.

Note also this approach is appropriate where a given schema is **one of many possible schemas** for the same underlying semantic model, and allows defining the model and logical constraints independently, with re-usable validation rules and unit testing advantages.

**A richer integration with the PyLODE documentation tool is planned to support generation of comprehensive documentation**

### Steps
- note that [bblock.json](bblock.json) needs no `ontology` entry: a file named `ontology.ttl` in the block directory is detected automatically
- examine file [ontology.ttl-example](ontology.ttl-example)
- rename to **ontology.ttl**
- run build
- run viewer
- navigate to "Exercise 10"/Ontology and examine `Classes` and `Properties`
- view validation results on "About
- view validation results at [Validation Report](validation) or [build-local/...](/register/build-local/tests/bbr/tutorial/exercise10_completed/_report.json)