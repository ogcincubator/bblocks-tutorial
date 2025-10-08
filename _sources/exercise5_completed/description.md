## Using a standard container

This is an **interoperable** approach to packaging a data model in a standardised structure.

i.e. the attributes (properties) are managed independently of the packaging container (Feature) 

In this case we use the schema from the previous examples.

This building block **inherits** reusable semantic annotations from a common library, simplifying implementation.

### Steps
- uncomment the reference to the previous exercise schema in schema.yaml
- run build, view etc
- examine "Semantic Uplift" and note that event though no `context.jsonld` is present the building block inherits and combines the two building blocks semantic annotations.



