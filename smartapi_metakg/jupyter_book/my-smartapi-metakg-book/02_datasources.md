# SmartAPI Data Sources 

## Introduction
The SmartAPI MetaKG integrates metadata from various biomedical APIs registered in the **[SmartAPI Registry](https://smart-api.info/)**. This section focuses on the expected structure of data sources, differences between TRAPI-compliant and non-TRAPI APIs, and how these standards impact integration into the MetaKG.

> The MetaKG pulls data from **SmartAPI-registered APIs**

## SmartAPI Registry

### Overview
The **[SmartAPI Registry](https://smart-api.info/)** is a repository of biomedical APIs that provides structured metadata. It acts as the foundation for identifying and integrating data sources into the MetaKG. Key metadata includes:
- **Endpoints**: URLs where the API can be accessed.
- **Methods**: HTTP methods (e.g., GET, POST) for interaction.
- **Input/Output Specifications**: Formats and schemas for data exchange.
- **Semantic Annotations**: Descriptions of the data entities and relationships exposed.

### Registering Your API

> *"SmartAPI uses OpenAPI-based specification for defining the key API metadata elements and value sets.
SmartAPIs leverages the Open API specification V3 and JSON-LD to provide semantically annotated JSON content that can be treated as Linked Data."*

To register your biomedical API in the SmartAPI Registry and integrate it into the MetaKG, follow these steps:

1. **Prepare Your API Documentation**: Ensure that your API follows the [OpenAPI Specification](https://swagger.io/specification/) and uses [JSON-LD](https://json-ld.org/) for semantic annotations.
2. **Submit to the SmartAPI Registry**: Visit the [SmartAPI Registry submission page](https://smart-api.info/register) and provide the required metadata, including:
   - **API Description**: A brief overview of the API and its functionality.
   - **Endpoints and Methods**: Specify accessible endpoints and the HTTP methods supported.
   - **Input and Output Formats**: Define the data formats your API uses (e.g., JSON, XML).
   - **Semantic Annotations**: Provide rich metadata for describing your data entities and relationships.
3. **Validation and Maintenance**  
   Validate your API metadata using the SmartAPI tools to ensure compliance. Update metadata as the API evolves to maintain compatibility with the MetaKG.

Once registered, your API becomes part of the MetaKG and can be queried alongside other biomedical data sources.

For more detailed instructions, check out the [SmartAPI Guide](https://smart-api.info/guide).

---

### Key Considerations for Data Registration
- **Consistency**: Use persistent and unique identifiers (e.g., `HGNC:12345` for genes).
- **Completeness**: Provide semantic annotations for all entities and relationships.
- **Validation**: Ensure your API metadata passes the validation checks for standardization.

---


#### **Examples of SmartAPI APIs**
- **[NCATS Biomedical Data Translator](https://smart-api.info/registry?q=translator)**
  - TRAPI-compliant APIs for querying biomedical knowledge graphs.
- **[Biothings APIs](https://smart-api.info/registry?q=biothings)**
  - High-performance APIs exposing gene, variant, and disease data.


---
## Expected Structure of Data Sources

### **Node Representation**

Nodes represent biomedical entities like genes, diseases, drugs, or pathways. Each node must have:
- **Unique Identifier**: A persistent ID (e.g., `HGNC:1100` for a gene).
- **Type**: The category of the node (e.g., `biolink:Gene`, `biolink:Disease`).

**Example**: A Gene node

```json
{
  "id": "HGNC:1100",
  "type": "biolink:Gene",
  "label": "BRCA1"
}
```

Each node must include:
- **Unique Identifier**: A persistent ID for cross-referencing.
- **Type**: The category of the node (e.g., `biolink:Gene`, `biolink:Disease`).


### Edge Representation

Edges represent relationships between nodes, such as:

- **Gene-disease associations** (e.g., `biolink:associated_with`)
- **Drug-target interactions** (e.g., `biolink:interacts_with`)

#### Key Edge Attributes:
- **Source and Target Nodes**: Defined by node identifiers.
- **Predicate**: Semantic relationship (e.g., `biolink:associated_with`).
- **Provenance**: Metadata indicating the source of the relationship.

#### Example: A Gene-Disease Relationship Edge

```json
{
  "source": "HGNC:1100", 
  "target": "MONDO:0005148", 
  "predicate": "biolink:associated_with",
  "provenance": {
    "source": "Monarch Initiative",
    "citation": "PMID:12345678"
  }
}
```
---

## TRAPI vs. Non-TRAPI APIs

### **TRAPI-Compliant APIs**
TRAPI APIs conform to the **[Translator Reasoner API (TRAPI)](https://github.com/NCATSTranslator/ReasonerAPI)** specification. Benefits include:
- Standardized input/output schemas based on graph data structures.
- Ability to handle complex graph queries.
- Compatibility with downstream tools in the NCATS Translator ecosystem.

**Overview**:  
TRAPI (Translator Reasoner API) APIs follow a standardized schema to enable seamless integration with graph-based biomedical systems. They allow for querying complex relationships between entities like genes, diseases, and drugs.

**Example**:  
The **NCATS Translator Reasoner API** provides TRAPI-compliant functionality.  
- **SmartAPI Link**: [NCATS Translator API](https://smart-api.info/registry?q=trapi)


<!-- #### Example: TRAPI Query
```json
{
  "message": {
    "query_graph": {
      "nodes": {
        "n0": {"categories": ["biolink:Disease"]},
        "n1": {"categories": ["biolink:Gene"]}
      },
      "edges": {
        "e0": {
          "subject": "n0",
          "object": "n1",
          "predicates": ["biolink:associated_with"]
        }
      }
    }
  }
}
``` -->
### Non-TRAPI APIs

Non-TRAPI APIs may contribute to the MetaKG but require additional processing to ensure compatibility:

1. **Mapping Metadata**: Align metadata with TRAPI-compatible structures, including defining nodes and edges.
2. **Transformations**: Adjust data formats and relationships to match MetaKG standards.

**Overview**:  
Non-TRAPI APIs do not natively follow the TRAPI schema but can still contribute to the MetaKG through metadata mapping and transformation.

**Example**:  
**Biothings APIs** expose structured gene and disease data but require adaptation for TRAPI integration.  
- **SmartAPI Link**: [Biothings APIs](https://smart-api.info/registry?q=biothings)

---

### Validating Your API for Registration

To register your biomedical API in the **SmartAPI Registry** and ensure it integrates seamlessly with the MetaKG, it is crucial to validate your OpenAPI v3 specification file. Below are the recommended validation steps:

---
