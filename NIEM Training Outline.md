# Pre-reqs?

For this class? A quiz?
For doing the IEPD process?

Scope of the class? Maybe a timeline? Explaining what a message is?

Water bottle metaphor?

Capture the payload.

Utilize existing scope of NIEM diagrams.


# Introduction

**This can mainly pull from the existing materials**

**Add a pre-req checklist for doing the development**

- Basic Intro
- What is NIEM
	- Existing slides
	- Scope of NIEM
		- OSI Slide _Get from [[Aubrey Beach]]?_
		- ![[OSI Diagram.png]]
		- Terminology clarification
		- Utilize existing scope of NIEM diagrams
		- Water bottle metaphor
- NIEM Harmonization and Organization
- Assumption of XML and XML Schema knowledge
	- _Where to point folks who don't have it?_
	- _Reference [[OJJDP]] slides on this for now?_
	- _IJIS still intends to do this?_

# IEPD Development

**This can mainly pull from the existing materials**

- Give overview of the process
	- Loop diagram and steps, describe each
	- Idealized: ![[DevSequence.svg]]
	- Realistic: ![[DevSequenceRealistic.svg]]

## Scenario Planning

**This can mainly pull from the existing materials**

- Example MOUs and the like
- Catalog-oriented metadata
	- This will return later when we build the IEPD

## Requirement Analysis

- Introduce the variety of UML diagrams
	- **Use existing slides**
- Give more detail on UML class diagrams
	- Only bare minimum knowledge of UML needed to start
	- Can start with business terms and structures
		- ![[CrashDriverClassDiagram.svg]]
		- Recommended, personally, to ensure that business concepts are recorded accurately
		- Translating those to NIEM isn't the goal in this step
	- Or can use NIEM terms and structures
		- ![[CrashDriverClassDiagram-NIEM.svg]]
		- Can save some time by doing some conversions at this step
		- Can confuse business experts
		- Potential for the developer to change requirements for the sake of NIEM mapping
	- _Reference [[OJJDP]] slides on this for now?_
	- Tools
		- [ArgoUML](https://en.wikipedia.org/wiki/ArgoUML)
		- [[BOUML]]
		- Visio / OmniGraffle
		- Mermaid / Dot
- Business rules
	- In whatever format you need
		- Schematron (which we will not get into)
			- e.g. Birth dates must be in the past, salutations matching gender
		- Just plain old narrative text
		- Other options? _I'm weak on this, need examples_
- Different processes can be followed from here
	- Step-by-step, e.g. finish mapping entirely before starting schemas
	- Concurrent, e.g. start building schemas as you go
	- We'll use something in-between, building an ersatz matching instance document as we map

**Up to this point, this has been a standard presentation.**

## Mapping

For this entire section, we'll look at various things in the mapping spreadsheet and show how to map them to NIEM or to new elements that we'll create later. As we move through, we'll cover all the major aspects of how NIEM works. **This is the backbone of the training, covering all the technical details of NIEM.**

### Intro to Mapping

- Introduce the mapping spreadsheet
	- Give options
		- Component Mapping Template
		- Simplified Training
		- Custom, which we'll be using here
	- Explain each column
	- The more you capture while mapping, the easier schema creation is down the road
	- Can use the template or roll your own simpler variety
		- Class/Attribute
		- Hierarchical
		- We'll use Class/Attribute, to match the UML
			- ![[CrashDriverClassDiagram.svg]]
- Enter business objects into mapping spreadsheet
	- _Show entering a few object, then switch to a pre-filled version_
- Handy to maintain a representation of the resulting instance document
	- Just indented text will work
		- [[instance_document_text]]
	- This is a visual representation of the IEP paths

### Mapping to Existing Objects

- What you are defines what you hold
	- ![[Type Hierarchy 01.png]]
	- ![[Type Hierarchy 02.png]]
	- ![[Type Hierarchy 03.png]]
	- ![[Type Hierarchy 04.png]]
	- ![[Type Hierarchy 05.png]]

#### Native properties

- Start with easy matches
- `nc:Person`, `nc:PersonName`, etc
- Show searching in SSGT
- _Show searching in Wayfarer?_
- _Show viewing objects in Grid-ML?_ (Grid-ML lacks global search)
- Show cardinality
- Show XML Schema representation (_in HyperNIEM?_)
	- [`nc:Person`](http://niem5.org/schemas/nc.html#Person)
	- [`nc:PersonType`](http://niem5.org/schemas/nc.html#PersonType)
	- [`nc:PersonName`](http://niem5.org/schemas/nc.html#PersonName)
	- [`nc:PersonNameType`](http://niem5.org/schemas/nc.html#PersonNameType)
	- [`nc:PersonSurName`](http://niem5.org/schemas/nc.html#PersonSurName)
- Show matching XML instance (_in oXygen?_)
	- _Should be able to validate this against the entire model_
- _Future: Show the same in JSON_
- Fill in `nc:Person`, `nc:PersonName`, `nc:Person(.*)Name`

#### Substitution groups

- Various means of representing a single concept
- `nc:PersonBirthDate` contains `nc:DateRepresentation` which is substituted by a variety of representations
	- Show the list: [`nc:DateRepresentation`](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o3-92a)
- _Show the schema for each of these_
	- [`nc:PersonBirthDate`](http://niem5.org/schemas/nc.html#PersonBirthDate)
	- [`nc:DateType`](http://niem5.org/schemas/nc.html#DateType)
	- [`nc:DateRepresentation`](http://niem5.org/schemas/nc.html#DateRepresentation)
- Fill in `nc:PersonBirthDate`, `nc:DateRepresentation`, and `nc:Date`

#### Inherited properties

- Start with `j:Crash`
- Fail to find "Crash Date"
- Introduce searching tips:
	- Synonyms
	- Word roots
	- Likely containers, like a Crash Date would be inside a Crash
	- Likely sub-elements
- Show date of a `j:Crash` via `nc:ActivityDate` in SSGT
- Explain namespaces
	- Because you start to really see them here
	- Don't have to be too detailed because this is just XML Schema
	- ![[Namespaces.png]]
- Inheritance
	- Each type has objects it contains: ![[Inheritance 01.png]]
	- No inheritance: ![[Inheritance 02.png]]
	- One level of inheritance: ![[Inheritance 03.png]]
	- Two levels of inheritance: ![[Inheritance 04.png]]
	- Three levels of inheritance: ![[Inheritance 05.png]]
- Show expansion of types in SSGT
- _Show expansion of types in Wayfarer?_
- Show XML Schema representation
	- [`j:Crash`](http://niem5.org/schemas/j.html#Crash)
	- [`j:CrashType`](http://niem5.org/schemas/j.html#CrashType)
	- [`j:DrivingIncidentType`](http://niem5.org/schemas/j.html#DrivingIncidentType)
	- [`nc:IncidentType`](http://niem5.org/schemas/nc.html#IncidentType)
	- [`nc:ActivityType`](http://niem5.org/schemas/nc.html#ActivityType)
	- [`nc:ActivityDate`](http://niem5.org/schemas/nc.html#ActivityDate)
- Show matching XML instance
- _Future: Show the same in JSON_
- Show `j:CommercialVehicle` as the deepest example
	- Show in SSGT [`j:CommercialVehicle`](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o3-dw)
	- Show in Wayfarer [`j:CommercialVehicle`](http://niem5.org/wayfarer/j/CommercialVehicle.html)
	- Temporarily replace `j:CrashVehicle` with this in the instance

#### Code tables

- `j:InjurySeverityCode`
- Show in schema
	- [`j:InjurySeverityCode`](http://niem5.org/schemas/j.html#InjurySeverityCode)
	- [`aamva_d20:AccidentSeverityCodeType`](http://niem5.org/schemas/aamva_d20.html#AccidentSeverityCodeType)
	- [`aamva_d20:AccidentSeverityCodeSimpleType`](http://niem5.org/schemas/aamva_d20.html#AccidentSeverityCodeSimpleType)
- The wrapping in a complex type leads directly to the infrastructure, which leads off the next section

### Linking things together

- Introduce Technical Framework
	- This is where the infrastructure come in
	- This shows the relationship between infrastructure, core, and domains
	- ![[NIEM Layers.png]]
- Referencing with `id` and `idref`
	- Diagrams and description
	- `nc:Person` and `j:Charge` as references in XML Schema
	- `nc:Person` and `j:Charge` as references in XML instance

#### Associations

- `j:PersonChargeAssociation`
- Added information specific to an association
	- `j:JuvenileAsAdultIndicator`
- Show `j:PersonChargeAssociation` in XML Schema
- Show `j:PersonChargeAssociation` in XML instance

#### Roles
	- `j:CrashPerson/nc:RoleOfPerson`

### Combining domains

- Show `exch:LicenseAugmentation` in XML Schema
- Show `exch:LicenseAugmentation` in XML instance
- _Need to make the augmentation use better, using multiple domains_

### Metadata - Information about information

- Explain conceptually
	- Document metadata as an example, that's easy in a classroom setting
	- Image metadata might be better
	- Image: ![[MicroUSB Cables Photo.jpg]]
	- Metadata for image: ![[MicroUSB Cables Photo Metadata.png]]
- Show `j:Metadata` in XML Schema
	- [`j:Metadata`](http://niem5.org/schemas/j.html#Metadata)
	- [`j:MetadataType`]http://niem5.org/schemas/j.html#MetadataType)
	- [`structures:MetadataType`](http://niem5.org/schemas/structures.html#MetadataType)
- Show `j:Metadata` in XML instance
- Discuss pros and cons
	- Easy to apply same metadata to many objects
	- Can result in messy many-to-many relationships
		- Powerful, but hard to implement
	
### Creating something new

- `priv:PrivacyMetadata/priv:PrivacyCode`
- ![[Element Flow Chart.png]]
- Creating simple data elements
	- `PrivacyCode` or `PersonDefenestrationIndicator` (**change this**)
	- Show hierarchical view of the simple types (_what did I mean by this?_)
- Creating complex objects
	- By extending existing NIEM objects
		- `PrivacyMetadata`
		- _Maybe there is a better, non-metadata example?_
	- From "scratch" (via `structures:ObjectType`)
		- `CrashDriverInfo` and `CrashDriverInfoType`
		- _Maybe there is a better non-root example?_
- Adding the new thing to the exchange
	- Implied Substitution Groups vs Concrete vs Augmentation
		- Will need standalone examples of each
		- Concrete: `priv:PrivacyCode` is concrete but very simple
		- Augmentation: `exch:PersonFictionalCharacterIndicator`
		- Implied Substitution Groups: _Not used in the IEPD, add?_

**Submit extensions that would be applicable to the whole model. Point to the issue tracker.**

### Bringing in external standards

- Rationale
	- Some folks just aren't going to change
	- Find a means to use those XML-based standards alongside NIEM
	- Wrap them up in NIEM-conformant wrappers
- Adapters
	- These are the wrappers
- Show `[nc:LocationGeospatialCoordinateAbstract]/geo:LocationGeospatialPoint/gml:Point`
	- NIEM: [`nc:LocationGeospatialCoordinateAbstract`](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o3-125z)
	- NIEM-conformant adapter: [`geo:LocationGeospatialPoint`](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o3-m73)
	- External standard: [`gml:Point`](https://tools.niem.gov/niemtools/ssgt/SSGT-GetProperty.iepd?propertyKey=o3-fux)

**Will have the complete instance document at this point as an indented text document.**

## Creating and Validating Schemas

- Show how the schemas fit together
	- Extension: ![[schema_import_01.png]]
	- Additional extensions: ![[schema_import_02.png]]
	- NIEM Core: ![[schema_import_03.png]]
	- Domains: ![[schema_import_04.png]]
	- Code Tables![[schema_import_05.png]]
	- External Standards: ![[schema_import_06.png]]
	- Infrastructure: ![[schema_import_07.png]]
- Schema subset
	- Explain concept
	- Create the actual subset live in the SSGT
		- _Maybe have some of it already completed via a wantlist?_
		- Export results
		- Explain wantlists
	- Demo linter
	- In-lining substitution groups by hand
		- Caveats
			- You've left the garden
			- Multiple validation passes
		- Point to that section in the spec for other options
- Extension and Exchange schemas
	- Create live in oXygen
		- Utilize pre-typed blocks
		- _Utilize Christina oXygen snippets?_
	- Required Attributes
		- `ct` for conformance target
		- `xmlns` for each
- Tips and Tricks
	- oXygen Snippets via Christina
	- BBEdit generation scripts via [[Tom Carlson]] **Need to update!**
		- Convert the [[instance_document_text]] to XML
		- `make-xml-4`
	- Using Schematron to check your work as you go
		- Do this and fix the inevitable errors
		- [Check NDR Conformance Using Schematron Validation](https://niem.github.io/reference/tools/oxygen/ndr/)
		- Download files from [reference.niem.gov](https://reference.niem.gov/niem/specification/naming-and-design-rules/5.0/niem-ndr-5.0.zip)
		- Use `ndr-rules-conformance-target-ext.sch` - Schematron rules for EXT schemas
			- Uses `ndr-functions.xsl`, so folks should grab the entire ZIP file, not just the schematron file

## Assembly

- [[Required Artifacts]]
- Message Builder Demo [[BAH]]
- Putting together by hand (ZIP file)
	- Show directory structure
	- iepd-catalog
	- conformance
	- changelog
	- readme

## Publishing

- Now
	- Show legacy repositories, for now
- Coming soon
	- Reg/Repo demo? [[GTRI]] _Won't be ready in time, future addition_
	- _Cover, but not demo, Restricted Reg/Repo?_
- _Maybe an area on GitHub?_
	- In the Community Blog?

## Implementation
- The existing materials essentially ¯\\\_(ツ)\_/¯
- This is a big issue and gap
- We need a plan for this
	- Leverage NTAC?
	- Leverage community?
	- Leverage internal GTRI devs?
- Could put the [[JAXB]] demo here, apply to the sample IEPD
	- _[[JAXB]] bindings need to be updated to a more current version of Java, a [[Peter Madruga]] thing_
- Add this later as part of the pre-recorded version?
- Could be separate classes, customized for different development environments
- **[[Katherine Escobar]]: Provide better directions on where to go next. Don't provide a lot of actual implementation detail, but don't just leave them hanging either.**

___

# Todo

- Fit in NIEM Conformance
	- NDR
	- IEPD Spec
	- Add Christina checklist
- Work contact information into sample IEPD
- Separate out an exchange schema from the extension
- Show tool alternatives to expensive software like oXygen/XMLSpy?





