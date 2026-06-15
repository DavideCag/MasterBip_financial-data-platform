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

## Motivation

This design mimics real-world CI/CD systems, ensuring:
- automation
- quality control
- reproducibility