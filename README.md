# Semantic Cataloging of Models using Large Language Models and Model Cards

This repository hosts the codebase for a Master’s thesis project at the Jheronimus Academy of Data Science (TU/e & TiU), supervised by Dr. I.P.K. Weerasingha Dewage. Titled *Semantic Cataloging of
Models using Large Language Models and Model Cards*, the project aims to improve AI model documentation using large language models (LLMs) and knowledge graphs. It targets Machine Learning, Deep Learning, and Data Engineering, with a planned publication in *IEEE Transactions on Knowledge and Data Engineering*.

## Table of Contents

- [Project Overview](#project-overview)
- [Purpose and Significance](#purpose-and-significance)
- [Repository Structure](#repository-structure)
- [Dependencies](#dependencies)
- [Setup](#setup)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact Information](#contact-information)

## Project Overview

The project addresses the lack of comprehensive model cards for AI models on platforms like Hugging Face, where only 44.2% of 74,970 models have model cards, despite accounting for 90.5% of downloads. These cards often miss critical details on biases, ethics, and environmental impacts. Using the [Model Card Report Ontology (MCRO)](https://github.com/UTHealth-Ontology/MCRO) and LLMs, the project automates the generation, completion, and discovery of semantic model cards. It employs a Design Science Research (DSR) methodology to create a tool enhancing transparency and accessibility.

**Research Question**: *To what extent can LLMs and model documentation be utilized to automatically generate, complete, compare, and discover semantic model cards?*

## Purpose and Significance

### Scientific Significance
- Advances automated model card generation.
- Structures documentation of biases, ethics, and environmental impacts.
- Supports transparency and accountability in AI research.

### Practical Significance
- Enhances documentation scalability and regulatory compliance.
- Improves accessibility for technical and non-technical users.
- Promotes awareness of AI’s societal and environmental impacts.

## Repository Structure

- **Ontology_mapper**: Generates RDF triples from Hugging Face model cards. See [README](Ontology_mapper/README.md).
- **KGQuerySystem**: Supports natural language querying of a GraphDB knowledge graph. See [README](KGQuerySystem/README.md).
- **RAG**: Implements a RAG pipeline with Neo4j for vector and Cypher queries. See [README](RAG/Readme.md).
- **.env.copy**: Environment variable template (rename to `.env`).
- **requirements.txt**: Python dependencies.

## Dependencies

- Python 3.8+
- `huggingface_hub`, `rdflib`, `requests`, `google-generativeai`, `langchain-community`, `langchain-google-genai`, `python-dotenv`

Install:

```bash
pip install -r requirements.txt
```

Required:
- GraphDB instance
- Neo4j database
- Gemini API key
- Hugging Face API token

## Setup

1. **Clone the repository**:

   ```bash
   git clone https://github.com/iamvishalsehgal/Enhancing-AI-Transparency.git
   cd Enhancing-AI-Transparency
   ```

2. **Configure environment**:
   - Rename `.env.copy` to `.env` and add:
     ```
     GEMINI_API_KEY=your_gemini_api_key
     GEMINI_MODEL_NAME=your_gemini_model_name
     HFTOKEN=your_huggingface_token
     GRAPHDB_ENDPOINT=your_graphdb_endpoint
     NEO4J_URI=your_neo4j_uri
     NEO4J_USER=your_neo4j_username
     NEO4J_PASSWORD=your_neo4j_password
     OUTPUT_BASE_PATH=your_output_base_path
     ```

3. **Prerequisites**:
   - Place `mcro.ttl` in `Ontology_mapper/Base_ontology/` from [MCRO repository](https://github.com/UTHealth-Ontology/MCRO).
   - Ensure GraphDB and Neo4j are accessible.

## Usage

Follow component-specific READMEs:
- **Ontology_mapper**: Run `Ontology_mapper/triple_creation.py`. See [README](Ontology_mapper/README.md).
- **KGQuerySystem**: Run `KGQuerySystem/KGQA.py`. See [README](KGQuerySystem/README.md).
- **RAG**: Run `RAG/RAG.py` and `RAG/query_runner.py`. See [README](RAG/Readme.md).


## Contributing

Contributions are limited due to the thesis scope. To contribute:
- Open an issue on [GitHub](https://github.com/iamvishalsehgal/Enhancing-AI-Transparency/issues).
- Follow coding style and update documentation.

## License

[MIT License](license)

## Contact Information

Open an issue on [GitHub](https://github.com/iamvishalsehgal/Enhancing-AI-Transparency/issues) or contact Vishal Sehgal via v.sehgal@student.tue.nl
