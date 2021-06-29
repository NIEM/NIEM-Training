## Sample

```
mmdc --input DevSequence.mmd --output DevSequence.svg --theme neutral
mmdc --input DevSequence.mmd --output DevSequence.png --theme neutral
mmdc --input DevSequenceRealistic.mmd --output DevSequenceRealistic.svg --theme neutral
mmdc --input DevSequenceRealistic.mmd --output DevSequenceRealistic.png --theme neutral
```

```
/Applications/Inkscape.app/Contents/Resources/bin/inkscape -z -e DevSequenceRealistic.png -w 1024 -h 1024 DevSequenceRealistic.svg
```

Best conversion use [[rsvg-convert]]:

```
rsvg-convert DevSequenceRealistic.svg > DevSequenceRealistic.png
rsvg-convert DevSequence.svg > DevSequence.png
```

From [Mermaid Sequence Diagrams](https://mermaid-js.github.io/mermaid/#/sequenceDiagram):

```mermaid
sequenceDiagram
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```

___

## IEPD Development Steps

### Steps as States
This isn't right. The steps should be the sequence arrows, with documents as each step.

```mermaid
sequenceDiagram
	Scenario Planning ->> Requirement Analysis: 
	Requirement Analysis ->> Mapping: 
	Mapping ->> Creating and Validating Schemas: 
	Creating and Validating Schemas ->> Assembly: 
	Assembly ->> Publishing: 
	Publishing ->> Implementing: 
```

### Artifacts as Steps

```mermaid
sequenceDiagram
	Agreement to Share ->> Source Documents: Scenario Planning
	Source Documents ->> Diagrams: Requirement Analysis
	Diagrams ->> Mapping Spreadsheet: Mapping
	Mapping Spreadsheet ->> Schemas: Creating and Validating Schemas
	Schemas ->> IEPD Package: Assembly
	IEPD Package ->> Repository Record: Publishing
```


```mermaid
sequenceDiagram
	Agreement to Share ->> Source Documents: Scenario Planning
	Source Documents ->> Diagrams: Requirement Analysis
	Diagrams ->> Mapping Spreadsheet: Mapping

	Mapping Spreadsheet -->> Diagrams: (forgot a piece of information)
	Diagrams ->> Mapping Spreadsheet: Mapping
	
	Mapping Spreadsheet -->> Source Documents: (missed a source document)
	Source Documents ->> Diagrams: Requirement Analysis
	Diagrams ->> Mapping Spreadsheet: Mapping


	Mapping Spreadsheet ->> Schemas: Creating and Validating Schemas
	
	Schemas -->> Mapping Spreadsheet: (did something weird while mapping that doesn't work in schema)
	
	Mapping Spreadsheet ->> Schemas: Creating and Validating Schemas
	
	Schemas ->> IEPD Package: Assembly
	IEPD Package ->> Repository Record: Publishing
```
