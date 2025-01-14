# Automated Detection of Microservice Architecture Antipatterns using Large Language Models
This repository supports the paper **"Automated Detection of Microservice Architecture Antipatterns using Large Language Models"**. It contains resources, examples, and evaluation results for detecting architectural antipatterns using Large Language Models (LLMs).

## Abstract
Detecting architectural antipatterns early in software development is critical for maintaining scalability, maintainability, and efficiency. While traditional tools focus on analyzing existing code, this study explores the potential of Large Language Models to identify architectural antipatterns in the design phase
using textual descriptions like PlantUML diagrams and OpenAPI documents. Three top-performing models - Claude 3.5 Sonnet, GPT-4o, and Gemini 1.5 Pro - were evaluated. CoT prompts incorporating a predefined antipattern catalog achieved the highest accuracy (72.2%). The models achieved a combined detection rate
of 55. 6% in 108 examples and provided actionable improvement suggestions in 75% of the cases. Detection accuracy and improvement quality varied based on input formats, with PlantUML Component Diagrams outperforming other formats. Antipatterns with clear structural markers, such as Shared Persistency, were more reliably detected and addressed, while complex patterns like Service Chain posed significant challenges. Although the results highlight the potential of Artificial Intelligence in architectural analysis, the generated suggestions require careful human review to ensure alignment with project-specific needs.

## Contents
The repository is structured as follows:
```plaintext
.
├── antipattern_examples
├── baseline_examples
├── evaluation
├── prompts
└── responses
```

### Baseline Examples
The `baseline_examples` directory contains a set of 6 examples. 
Two examples are provided for each of the following input formats:
- PlantUML Component Diagrams
- PlantUML Sequence Diagrams
- OpenAPI Documents

And for each input format there is one fictional example and one real-world example.
The following examples are used in this project for detecting architectural antipatterns:
- **[Netflix Video Processing](baseline_examples/netflix_video_processing.puml)**  
  Format: *PlantUML Component Diagram*  
  Source: [Netflix Tech Blog](https://netflixtechblog.com/rebuilding-netflix-video-processing-pipeline-with-microservices-4e5e6310e359)

- **[Ecommerce](baseline_examples/ecommerce.puml)**  
  Format: *PlantUML Component Diagram*  
  Source: [GCP Microservice Demo](https://github.com/GoogleCloudPlatform/microservices-demo)

- **[2PC (Two-Phase Commit)](baseline_examples/2pc.puml)**  
  Format: *PlantUML Sequence Diagram*  
  Source: [Red Hat Developers](https://developers.redhat.com/blog/2018/10/01/patterns-for-distributed-transactions-within-a-microservices-architecture#possible_solutions)

- **[Ledger](baseline_examples/ledger.puml)**  
  Format: *PlantUML Sequence Diagram*  
  Source: [Uber Tech Blog](https://www.uber.com/en-DE/blog/how-ledgerstore-supports-trillions-of-indexes/?uclick_id=93ac841a-6cee-4c7b-8cb5-63870bbcf4c7)

- **[Museum API](baseline_examples/museum.openapi.yaml)**  
  Format: *OpenAPI Document*  
  Source: [Redocly Example Project](https://github.com/Redocly/museum-openapi-example)

- **[Twilio API](baseline_examples/twilio.openapi.yaml)**  
  Format: *OpenAPI Document*  
  Source: [Twilio GitHub Repository](https://github.com/twilio/twilio-oai/blob/main/spec/yaml/twilio_voice_v1.yaml)

---
### Antipattern Examples
The `antipattern_examples` directory contains a set of 102 examples, each illustrating specific microservice architecture antipatterns. These examples are categorized based on the type of antipattern and the input format used (PlantUML Component Diagrams, PlantUML Sequence Diagrams, or OpenAPI Documents). Each example is designed to test the detection capabilities of LLMs across various scenarios.

### Prompts
The `prompts` directory includes the different prompt configurations used during the evaluation of LLMs. This comprises:
* Standard Prompts: Role-based prompts where the LLM is assigned the role of an IT Architect specializing in microservice architectures.
* CoT Prompts: Prompts that combine role-based prompting with Chain-of-Thought reasoning and one-shot prompting, providing step-by-step instructions and illustrative examples.
* CoT+Catalog Prompts: An extension of CoT prompts that includes a predefined antipattern catalog to establish a common vocabulary.

### Responses
The `responses` directory contains the outputs generated by the LLMs in response to the prompts provided.

### Evaluation
The `evaluation` directory includes the [raw results](evaluation/evaluation_results.csv).
Furthermore, the results are evaluated and visualized in the [evaluation notebook](evaluation/evaluation.ipynb).
