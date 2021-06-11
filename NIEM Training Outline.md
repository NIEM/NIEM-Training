## General Idea

Focus on Message Spec/IEPD Development as the framework or backbone, bringing in NIEM concepts as part of that process as needed, particularly in the mapping phase.

This is a large change from past training programs, which treated the technical aspects of NIEM as essentially a separate topic from the IEPD-creation process.

Use an actual example Message Spec as the framework for the whole thing. Tentatively starting with [Crash Driver IEPD](https://github.com/iamdrscott/CrashDriver) from [[Dr. Scott]].

### Potential IEPDs to Use

- Requirements:
	- Needs to cover _all_ technical features of NIEM
	- General purpose, understandable to all
		- Uses domains
		- But not overly specific to one
	- Real world scenario, but not required to be a "real" IEPD
		- Actual in-use IEPD may be problematic because we'll change it for the training
	- Covers the big three objects:
		- People
		- Locations
		- Activities
	- Small enough to understand in class
- Possibilities:
	- Crash Driver IEPD from [[Dr. Scott]]
		- Covers nearly all NIEM features, by design
			- Ensure external standards work
			- Improve augmentations
			- Replace "fictional" indicator
		- Justice-specific, but not objectionably so
		- Juvenile aspect so as to bring in HS? Learners permit?
	- Amber Alert
		- Currently NIEM 3? [Amber Alert sample message from Nlets](https://wiki.nlets.org/index.php/Section_34:_Amber_Alert#Amber_Alert_NIEM_Examples).
		- Justice-specific
		- Doesn't use referencing and some more esoteric features
	- Severe weather
		- Good general purpose concept
			- We're not experts on the real-world content, though
		- Could utilizes EM domain
		- Not much in NIEM for this
	- SBA loans for COVID
		- Not general knowledge
		- Short-term interest
	- Insurance Claim IEPD from [[Webb Roberts]]?
		- Could not find this anywhere
	- Superhero IEPD
		- Not real-world

___

# Detailed Outline

## Introduction

- Basic Intro
- What is NIEM
	- OSI Slide
- NIEM Harmonization and Organization
- Assumption of XML and XML Schema knowledge
	- _Reference [[OJJDP]] slides on this for now?_

## Scenario Planning

- Example MOUs and the like
- Catalog-oriented metadata
	- This will return later when we build the IEPD
- This can mainly pull from the existing materials

## Requirement Analysis

- Create UML diagram
	- Bare minimum of UML needed to start
	- _Reference [[OJJDP]] slides on this for now?_
- Business rules
	- In whatever format you need
		- Schematron (which we will not get into)
			- Show some common examples?
		- Just plain old narrative text
- Cover process differences?
	- Step-by-step, e.g. finish mapping entirely before starting schemas
	- Concurrent, e.g. start building schemas as you go
	- While things are separated into discrete steps, the border is fuzzy
		- Document business objects by entering them into the mapping template, is that Requirement Analysis or Mapping?
	- Introduce the template?


## Mapping

For this entire section, we'll look at various things in the mapping spreadsheet and show how to map them to NIEM or to new elements that we'll create later. As we move through, we'll cover all the major aspects of how NIEM works.

- Show a few different mapping spreadsheet options
	- Class/Attribute
	- Hierarchical
- Enter business objects into mapping spreadsheet?

### Mapping to Existing Objects

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
		- _Pull diagrams from existing slides_
	- Show expansion of types in SSGT
	- _Show expansion of types in Wayfarer?_
	- Show XML Schema representation
	- Show matching XML instance
	- _Future: Show the same in JSON_
	- Show `j:CommercialVehicle` as the deepest example
		- Temporarily replace `j:CrashVehicle` for this
- Code tables
	- `j:InjurySeverityCode`

### Linking things together

- _Introduce Technical Framework here?_
	- This shows the relationship between infrastructure, core, and domains
	- _Pull diagrams from existing slides_
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

### Combining domains

- Show `exch:LicenseAugmentation` in XML Schema
- Show `exch:LicenseAugmentation` in XML instance
- _Need to make the augmentation use better, using multiple domains_

### Information about information

- Metadata
	- Explain conceptually
	- Show `j:JusticeMetadata` in XML Schema
	- Show `j:JusticeMetadata` in XML instance
	
### Creating something new

- `priv:PrivacyMetadata/priv:PrivacyCode`
- Creating simple data elements
	- `PrivacyCode` or `PersonFictionalCharacterIndicator` (**change this**)
	- Show hierarchical view of the simple types
- Creating complex objects
	- From existing NIEM objects
		- `PrivacyMetadata`
		- _Maybe there is a better, non-metadata example?_
	- From scratch (via `structures:ObjectType`)
		- `CrashDriverInfo` and `CrashDriverInfoType`
		- _Maybe there is a better non-root example?_
- Adding the new thing to the exchange
	- Implied Substitution Groups vs Concrete vs Augmentation
		- Will need standalone examples of each
		- Concrete: `priv:PrivacyCode` is concrete but very simple
		- Augmentation: `exch:PersonFictionalCharacterIndicator`
		- Implied Substitution Groups: _Not used in the IEPD, add?_

### Bringing in external standards

- Using adapters
- Sample uses `nc:Location2DGeospatialCoordinate`?
	- _This isn't from Geospatial_
	- _Need to replace it with `[nc:LocationGeospatialCoordinateAbstract]/geo:LocationGeospatialPoint/gml:Point` in the instance_
	- _Schemas are set up, but need to specifically add in the adapter and verify that it works_

**Will have the complete instance document at this point.**

## Creating and Validating Schemas

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
		- [[Christina Medlin]] is a genius
		- #todo **Get the materials from her for modification/inclusion**

## Assemble

- Required documents
	- catalog
	- _Look up the rest_
- Message Builder Demo [[BAH]]
- Putting together by hand (ZIP file)
	- Show directory structure

## Publish

- Reg/Repo demo [[GTRI]]
- Cover, but not demo, Restricted Reg/Repo
- Show legacy repositories, for now

## Implement
- The existing materials essentially ¯\\\_(ツ)\_/¯
- This is a big issue and gap
- We need a plan for this
	- Leverage NTAC?
	- Leverage community?
	- Leverage internal GTRI devs?
- Could put the [[JAXB]] demo here, apply to the sample IEPD
- Add this later as part of the pre-recorded version?
- Could be separate classes, customized for different development environments

___

## Concepts to still fit in

- NIEM Conformance
- NIEM Technical Framework
	- Content Models?
- Work contact information into this IEPD
- Show tool alternatives to expensive software like oXygen

## Separate videos for later

- [[JAXB]]
- [[CUI]]






