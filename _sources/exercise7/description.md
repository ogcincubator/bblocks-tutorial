## Exercise 7

Goal: Examine [transform support](https://ogcincubator.github.io/bblocks-docs/create/transforms)

Note: User Experience for FAIR transform publishing is a work in progress - feel free to [contribute](https://github.com/ogcincubator/bblocks-tutorial/issues) ideas!

### Steps
- See the documentation on [transform support](https://ogcincubator.github.io/bblocks-docs/create/transforms)
- rename [transforms.example](context.example) to [transforms.yaml](context.jsonld)
- run build
- run viewer
- navigate to [Transforms](/bblock/ogc.bbr.tutorial.exercise7/transforms) Tab
- examine transforms available
- note how each transform supports specific input formats - e.g. an XSLT transform will be applied to XML
- navigate to [Examples](/bblock/ogc.bbr.tutorial.exercise7/examples) Tab
- click on `Transform Results` button
- Select the transform (drop down list) and view results

### further development

In future there is expected to be a finer-grained binding of transforms to input and output profiles for data conformance, and integrated validation.

Also a "plug-in" custom transform capability is planned - allowing CI/CT of multiple transformation testing as part of specification development or augmentation of resources supporting implementations.

