# CI/CD Pipeline

We designed a multi-stage CI/CD pipeline using GitHub Actions.

## Pipelines

### C++ Pipeline
- Builds the project using CMake
- Executes unit tests (Google Test)
- Generates a JSON report
- Uploads artifact

### Python Pipeline
- Triggered after C++ pipeline (workflow_run)
- Downloads the generated artifact
- Validates JSON output
- Executes pytest tests

## Key Features

- Matrix build (multiple OS and configurations)
- Dependency caching
- Artifact sharing between workflows
- Static analysis of the code
- Final summary generation on GitHub

## Motivation

This design mimics real-world CI/CD systems, ensuring:
- automation
- quality control
- reproducibility


## Flowchart
```mermaid

flowchart LR
    A((Code Push)) --> B[Build]
    B --> C[Test]
    C -->|OK| D[Deploy]
    C -->|Fail| A
    D --> E((Production))