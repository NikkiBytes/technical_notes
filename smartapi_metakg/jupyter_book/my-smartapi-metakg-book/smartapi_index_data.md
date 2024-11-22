# SmartAPI Index Data

This section provides insights into the structure and content of indices stored in Elasticsearch for SmartAPI. We explore three key indices:

- `smartapi_metakg_docs_consolidated`
- `smartapi_metakg_docs`
- `smartapi_docs`

---

## **Index: `smartapi_metakg_docs_consolidated`**

### **Document Count**
- **Total Documents**: 23,434

### **Sample Fields**
| **subject** | **object**               | **predicate**       | **api**                                      | **subject_prefix** | **object_prefix** |
|-------------|--------------------------|---------------------|----------------------------------------------|--------------------|-------------------|
| Gene        | GrossAnatomicalStructure | expressed_in        | Monarch API                                 | HGNC               | UBERON            |
| Disease     | PhenotypicFeature        | has_phenotype       | Monarch API                                 | MONDO              | HP                |

---

## **Index: `smartapi_metakg_docs`**

### **Document Count**
- **Total Documents**: 99,724

### **Sample Fields**
| **subject** | **object**               | **predicate**       | **api**                                      | **subject_prefix** | **object_prefix** |
|-------------|--------------------------|---------------------|----------------------------------------------|--------------------|-------------------|
| Gene        | GrossAnatomicalStructure | expressed_in        | Monarch API                                 | HGNC               | UBERON            |
| Disease     | PhenotypicFeature        | has_phenotype       | Monarch API                                 | MONDO              | HP                |

---

## **Index: `smartapi_docs`**

### **Document Count**
- **Total Documents**: 271

### **Sample Fields**
| **openapi** | **info**                 | **servers**                                         | **tags**               | **paths**       |
|-------------|--------------------------|----------------------------------------------------|------------------------|-----------------|
| 3.0.3       | TRAPI/Reasoner API       | https://bte.transltr.io/v1                         | TRAPI v1.5.0           | /meta_knowledge_graph |

---

### **Summary**
This data highlights how SmartAPI indices are organized and the types of data stored. The indices provide metadata, knowledge graph relationships, and API definitions crucial for enabling seamless integrations with SmartAPI's MetaKG.

