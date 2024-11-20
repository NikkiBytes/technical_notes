# Understanding the SmartAPI MetaKG

This section explores the background, data sources, and architecture of the SmartAPI MetaKG index, highlighting its significance in biomedical research.

## Background

The SmartAPI MetaKG index is a metadata-driven knowledge graph built to unify data from diverse biomedical APIs. By structuring API metadata into a graph, it enables researchers to explore interconnections between biomedical entities such as genes, diseases, and drugs. 

Knowledge graphs like MetaKG are crucial for:
- **Integrating heterogeneous data**: Connecting diverse datasets with standardized metadata.
- **Facilitating discovery**: Allowing researchers to uncover relationships between concepts.
- **Enabling computational tools**: Supporting AI and machine learning by providing structured, machine-readable knowledge.

## Data Sources

The MetaKG integrates metadata from APIs registered in [SmartAPI](https://smart-api.info). Key data sources include:
- Gene-disease associations from databases like Monarch Initiative.
- Drug-target data from DrugBank.
- Pathway information from Reactome.

By combining these resources, the MetaKG creates a comprehensive map of biomedical relationships.

## Architecture

The architecture of the SmartAPI MetaKG involves several key components:
1. **SmartAPI Metadata Parser**: Extracts and standardizes API metadata.
2. **MetaKG Index**: Organizes metadata into a graph structure.
3. **Query Modules**: Enables pathfinding and exploration.

Below is a diagram illustrating the architecture. For an interactive look at the MetaKG's workflow, open the linked notebook.

![MetaKG Architecture](images/metakg_architecture.png)

[Explore the Architecture](architecture.ipynb)

---
