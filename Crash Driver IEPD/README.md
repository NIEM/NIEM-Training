# Crash Driver Report IEPD

This example IEPD is designed for the training program. It exercises most of the features in the NDR:

- Adapters
- Associations
- Augmentations
	- Augmentation elements
	- Augmentations substitutable for an augmentation point
- Elements with attributes
	- With simple content
	- With complex content
	- Metadata
	- Single metadata pointer
	- Multiple metadata pointers
- References
- Repeated elements

Not exercised yet and perhaps too esoteric for the training class:

- `structures:relationshipMetadata`
- `xs:list`
- `xml:base`
- `xml:lang`
- `xml:space`
- `xsi:type`

The JSON files in the `json` directory were originally translated from the sample IEPs by:

```bash
niemtool translate CrashDriver.no iep-sample/iep1.xml > json/iep1.json
```

Current version was manually updated from those original files to match the XML version.



