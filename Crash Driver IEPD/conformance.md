# IEPD Conformance Assertion

Assertion: This NIEM IEPD is certified to conform to the following NIEM
specifications:

- [Conformance 5.0](https://reference.niem.gov/niem/specification/conformance/5.0/)
- [Naming and Design Rules (NDR) v5.0](https://reference.niem.gov/niem/specification/naming-and-design-rules/5.0/)
- [Information Exchange Package Description (IEPD) v5.0](https://reference.niem.gov/niem/specification/model-package-description/5.0/)

Author: [Tom Carlson](mailto:tom@tomcarlsonconsulting.com)

Certified by: [Tom Carlson](mailto:tom@tomcarlsonconsulting.com)

Certification date: 2021-09-17

Details of conformance verification

1. How NIEM conformance was verified:
	a. Automatic (tool) checks were performed with XML Schema tools identified below.
	b. Manual (subjective) checks on conformance rules were performed by the author/certifier.
	c. A general manual (and subjective) cross-check for adherence to conformance rules and quality assurance was performed by a colleague of the author who understands NIEM and XML Schema.
	d. Business requirements associated with the information exchange defined by this IEPD were verified by the author.

2. Tools employed:
	a. NIEM Schema Subset Generator (SSGT) (for NIEM 3.0) generated all subset schema documents.
	b. oXygen XML Developer was used to cross-validate XML schemas and XML instances.
	c. Xerces 2.7.0-0 was used for cross-validation of XML schemas and XML instances.

3. Results:
	a. No known major issues remain.
	b. All XML artifacts are well-formed and valid.
	c. Author and SMEs verified that several warnings by tools are not relevant to this IEPD.
	e. `CrashDriver.xsd` passes NDR tests for an extension schema
	f. `extension.xsd` passes NDR tests for an extension schema
	g. `iepd-catalog.xml` is valid against `iepd-catalog.xsd` for version 5.0
