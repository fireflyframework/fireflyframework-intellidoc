# fireflyframework-intellidoc

**Intelligent Document Processing framework powered by VLMs/LLMs.**

Built on [pyfly](https://github.com/fireflyframework/pyfly) and [fireflyframework-genai](https://github.com/fireflyframework/fireflyframework-genai).

> Copyright 2026 Firefly Software Solutions Inc — Apache License 2.0

## Overview

fireflyframework-intellidoc is a production-grade IDP framework that leverages Vision-Language Models
to ingest, classify, split, extract, validate, and manage documents of any type. It is fully
catalog-driven: document types, extraction schemas, and validation rules are managed through REST APIs.

## Features

- **Catalog-Driven** — Document types, extraction schemas, and validators configured at runtime via APIs
- **VLM-First** — Uses vision-language models for document understanding, classification, and extraction
- **Multi-Source Ingestion** — Local files, URLs, S3, Azure Blob, GCS
- **Processing Pipeline** — DAG-based pipeline: ingest → preprocess → split → classify → extract → validate → persist
- **Hexagonal Architecture** — All infrastructure behind ports; swap adapters without changing business logic
- **Built on pyfly** — DI container, web layer, data persistence, messaging, security, observability
- **Built on fireflyframework-genai** — Agents, pipeline engine, tools, reasoning patterns

## Installation

```bash
# Core
pip install fireflyframework-intellidoc

# With all features
pip install "fireflyframework-intellidoc[all]"

# Development
pip install "fireflyframework-intellidoc[dev]"
```

## Quick Start

```python
from pyfly.core import PyFlyApplication, pyfly_application


@pyfly_application(
    name="my-idp-service",
    scan_packages=["myapp", "fireflyframework_intellidoc"],
)
class MyIDPApp:
    pass


app = PyFlyApplication(MyIDPApp)
```

## License

Apache License 2.0 — Copyright 2026 Firefly Software Solutions Inc
