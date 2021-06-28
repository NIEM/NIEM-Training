## Sample

```
mmdc --input DevSequence.mmd --output DevSequence.svg --theme neutral
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
	Desire ->> Source Documents: Scenario Planning
	Source Documents ->> Diagrams: Requirement Analysis
	Diagrams ->> Mapping Spreadsheet: Mapping
	Mapping Spreadsheet ->> Schemas: Creating and Validating Schemas
	Schemas ->> IEPD Package: Assembly
	IEPD Package ->> Repository Record: Publishing
```

