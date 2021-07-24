# Crash Driver Report IEPD

This example IEPD is designed for showing conversion between NIEM XML, NIEM JSON, and NIEM RDF.
It exercises most of the features in the NDR:

* Adapters
* Associations
* Augmentations
  - Augmentation elements
  - Augmentations substitutable for an augmentation point
* Elements with attributes
  - With simple content
  - With complex content
* Metadata
  - Single metadata pointer
  - Multiple metadata pointers
* References
* Repeated elements

Not exercised yet:

* `structures:relationshipMetadata`
* `xs:list`
* `xml:base`
* `xml:lang`
* `xml:space`
* `xsi:type`

`CrashDriver.no` is a "NIEM object" file compiled by:
`niemtool compile xml-catalog.xml extension/CrashDriver.xsd`

The JSON files in the `json` directory were translated from the sample IEPs by:
`niemtool translate CrashDriver.no iep-sample/iep1.xml > json/iep1.json`


