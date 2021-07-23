# NIEM Training Detailed Outline

## Introduction

- Basic Intro
- What is NIEM
	- OSI Slide
- NIEM Harmonization and Organization
- Assumption of XML and XML Schema knowledge
	- _Reference [[OJJDP]] slides on this for now?_

## IEPD Development

- Give overview of the process
	- Idealized: ![[DevSequence.svg]]
	- Realistic: ![[DevSequenceRealistic.svg]]

### Scenario Planning

- Example MOUs and the like
- Catalog-oriented metadata
	- This will return later when we build the IEPD
- This can mainly pull from the existing materials

### Requirement Analysis

- Create UML class diagram
	- Only bare minimum of UML needed to start
	- Can start with business terms and structures
		- ![[CrashDriverClassDiagram.svg]]
	- Or can use NIEM terms and structures
		- ![[CrashDriverClassDiagram-NIEM.svg]]
	- _Reference [[OJJDP]] slides on this for now?_
- Business rules
	- In whatever format you need
		- Schematron (which we will not get into)
			- Show some common examples?
		- Just plain old narrative text
- Cover process differences?
	- Step-by-step, e.g. finish mapping entirely before starting schemas
	- Concurrent, e.g. start building schemas as you go
	- We'll use something in-between, building a matching instance document as we map
	- While things are separated into discrete steps, the border is fuzzy
		- Document business objects by entering them into the mapping template, is that Requirement Analysis or Mapping?
	- Introduce the mapping template here?


### Mapping

For this entire section, we'll look at various things in the mapping spreadsheet and show how to map them to NIEM or to new elements that we'll create later. As we move through, we'll cover all the major aspects of how NIEM works.

- Show a few different mapping spreadsheet options
	- Class/Attribute
	- Hierarchical
	- We'll use Class/Attribute, to match UML closer
- Enter business objects into mapping spreadsheet?

#### Mapping to Existing Objects

- Native properties
	- `nc:Person`, `nc:PersonName`, etc
	- Show searching in SSGT
	- _Show searching in Wayfarer?_
	- Show cardinality
	- Show XML Schema representation (_in Wayfarer?_)
	- Show matching XML instance (_in oXygen?_)
	- _Future: Show the same in JSON_

- Inherited properties
	- Date of a `j:Crash` via `nc:ActivityDate`
	- Explain namespaces
		- Because you start to really see them here
		- ![[Namespaces.png]]
	- Diagrams, **but update to NIEM 5.0**
		- Each type has objects it contains: ![[Inheritance 01.png]]
		- No inheritance: ![[Inheritance 02.png]]
		- One level of inheritance: ![[Inheritance 03.png]]
		- Two levels of inheritance: ![[Inheritance 04.png]]
		- Three levels of inheritance: ![[Inheritance 05.png]]
	- Show expansion of types in SSGT
	- _Show expansion of types in Wayfarer?_
	- Show XML Schema representation
	- Show matching XML instance
	- _Future: Show the same in JSON_
	- Show `j:CommercialVehicle` as the deepest example
		- Temporarily replace `j:CrashVehicle` for this
- Code tables
	- `j:InjurySeverityCode`

#### Linking things together

- _Introduce Technical Framework here?_
	- This shows the relationship between infrastructure, core, and domains
	- ![[NIEM Layers.png]]
- Referencing with `id` and `idref`
	- Diagrams and description
	- `nc:Person` and `j:Charge` as references in XML Schema
	- `nc:Person` and `j:Charge` as references in XML instance
- Associations
	- `j:PersonChargeAssociation`
	- Added information specific to an association
		- `j:JuvenileAsAdultIndicator`
	- Show `j:PersonChargeAssociation` in XML Schema
	- Show `j:PersonChargeAssociation` in XML instance
- Roles
	- `j:CrashPerson/nc:RoleOfPerson`

#### Combining domains

- Show `exch:LicenseAugmentation` in XML Schema
- Show `exch:LicenseAugmentation` in XML instance
- _Need to make the augmentation use better, using multiple domains_

#### Information about information

- Metadata
	- Explain conceptually
		- Document metadata as an example, that's easy in a classroom setting
		- Image metadata might be better
		- Image: ![[MicroUSB Cables Photo.jpg]]
		- Metadata for image: ![[MicroUSB Cables Photo Metadata.png]]
	- Show `j:JusticeMetadata` in XML Schema
	- Show `j:JusticeMetadata` in XML instance
	- Discuss pros and cons
		- Easy to apply same metadata to many objects
		- Can result in messy many-to-many relationships
	
#### Creating something new

- `priv:PrivacyMetadata/priv:PrivacyCode`
- ![[Element Flow Chart.png]]
- Creating simple data elements
	- `PrivacyCode` or `PersonFictionalCharacterIndicator` (**change this**)
	- Show hierarchical view of the simple types (_what did I man by this?_)
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

#### Bringing in external standards

- Rationale
	- Some folks just aren't going to change
	- Find a means to use those XML-based standards alongside NIEM
	- Wrap them up in NIEM-conformant wrappers
- Adapters
	- These are the wrappers
- Show `[nc:LocationGeospatialCoordinateAbstract]/geo:LocationGeospatialPoint/gml:Point`
	- NIEM: `nc:LocationGeospatialCoordinateAbstract`
	- NIEM-conformant adapter: `geo:LocationGeospatialPoint`
	- External standard: `gml:Point`

**Will have the complete instance document at this point.**

### Creating and Validating Schemas

- Show how the schemas fit together
	- Extension: ![[schema_import_01.png]]
	- Additional extensions: ![[schema_import_02.png]]
	- NIEM Core: ![[schema_import_03.png]]
	- Domains: ![[schema_import_04.png]]
	- Code Tables![[schema_import_05.png]]
	- External Standards: ![[schema_import_06.png]]
	- Infrastructure: ![[schema_import_07.png]]
- Schema subset
	- Create the actual subset live in the SSGT
		- _Maybe have some of it already completed?_
		- Export
		- Explain wantlists
	- In-lining substitution groups by hand
		- Caveats
		- Point to that section in the spec
- Extension and Document schemas
	- Create live in oXygen
		- Utilize pre-typed blocks
		- Utilize [[Christina Medlin]] oXygen snippets
- Tips and Tricks
	- oXygen Snippets
	- BBEdit generation scripts
	- Using Schematron to check your work as you go
		- [Check NDR Conformance Using Schematron Validation](https://niem.github.io/reference/tools/oxygen/ndr/)
		- Download files from [reference.niem.gov](https://reference.niem.gov/niem/specification/naming-and-design-rules/5.0/niem-ndr-5.0.zip)
		- Use `ndr-rules-conformance-target-ext.sch` - Schematron rules for EXT schemas
			- Uses `ndr-functions.xsl`, so folks should grab the entire ZIP file, not just the schematron file

### Assembly

- Required documents
	- catalog
	- _Look up the rest_
- Message Builder Demo [[BAH]]
- Putting together by hand (ZIP file)
	- Show directory structure

### Publishing

- Reg/Repo demo? [[GTRI]] _Won't be ready in time, future addition_
- Cover, but not demo, Restricted Reg/Repo
- Show legacy repositories, for now

### Implement
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

## Concepts to still fit in

- NIEM Conformance
- NIEM Technical Framework
	- Content Models?
- Work contact information into this IEPD
- Show tool alternatives to expensive software like oXygen?

## Separate videos for later

- [[JAXB]]
- [[CUI]]






