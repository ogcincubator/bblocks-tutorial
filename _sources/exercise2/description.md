## Exercise 2

Goal: Semantically annotate a JSON schema

[JSON-LD](https://json-ld.org/) **maps JSON data structures to URI**s - which in turn can reference semantic descriptions of those elements.

(It can also map content to URIs - taking keywords and turning them into Linked Data)

The challenge is that these mappings become exponentially harder to build and test as the JSON structure deepens - and common structures may be mapped different ways to different descriptions - unless **FAIR JSON-LD mappings** are created, and **tooling simplifies the complexity**.

Enter the OGC Building Blocks!  The (only, currently) tool that will combine simple schemas and JSON-LD contexts into an application-ready bundle!

### Steps
- rename [context.example](context.example) to [context.jsonld](context.jsonld)
- run build
- run viewer
- navigate to [Examples](/bblock/ogc.bbr.tutorial.exercise2/examples) tab
- choose "RDF/Turtle" to see generated RDF
- navigate to [Semantic Uplift](/bblock/ogc.bbr.tutorial.exercise2/semantic-uplift) tab (present in completed example)
- view validation results at [build-local/...](/register/build-local/tests/bbr/template/exercise2/_report.json)