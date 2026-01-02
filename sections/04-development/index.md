---
title: Development
has_children: false
nav_order: 5
---

## DVCS (Distributed Version Control System)

The project utilizes **Git** for version control, hosted on GitHub. To ensure a clear *Separation of Concerns*, the project adopts a multi-repository strategy:

* **`artifact`**: Contains the source code, including the Python package (`edge_ids`) and the Embedded Firmware. It serves as the single source of truth for the software implementation.
* **`report`**: Contains the documentation source files. Keeping documentation separate prevents codebase pollution and allows for independent versioning of the report.

**Commit Convention**
The development workflow strictly adheres to the **Conventional Commits** specification. Commit messages follow the structure `type: description` (e.g., `feat: add scraper`, `chore: setup poetry`), enabling semantic versioning and automated changelog generation.

## Technological details

### Programming Language: Python 3
**Python (v3.12+)** has been selected as the primary language for the Edge Intrusion Detection System due to its dominance in the Machine Learning ecosystem and rich support for network programming.

### Dependency Management: Poetry
To address the "Dependency Hell" problem and ensure **Reproducibility**, the project uses **Poetry** instead of standard `pip` requirements.
* **`pyproject.toml`**: Declares high-level dependencies (e.g., `requests`).
* **`poetry.lock`**: locks the exact versions of all sub-dependencies. This guarantees that the software behaves exactly the same on the developer's machine, the CI/CD pipeline, and the target environment.

### Libraries
* **`requests`**: Used for the *Web Scraping* module. It provides a high-level abstraction over HTTP/1.1 protocols, simplifying the retrieval of Threat Intelligence blocklists compared to raw socket programming.
