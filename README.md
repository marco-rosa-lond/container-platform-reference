# Container Platform Reference (CPR)

> **Build once. Document always. Recover with confidence.**

## Overview

The Container Platform Reference (CPR) is the engineering standard for building, operating, maintaining, and recovering the organization's container platform.

This repository is the single source of truth for the platform. It contains the documentation, standards, templates, and bootstrap procedures required to deploy and operate a consistent container environment.

The platform is designed around four principles:

- Simplicity
- Consistency
- Reproducibility
- Recoverability

---

## Technology Stack

| Component | Technology |
|----------|------------|
| Operating System | Ubuntu Server LTS |
| Container Runtime | Docker Engine |
| Container Management | Portainer CE |
| Source Control | Git |
| Documentation | Markdown |
| Documentation Editor | Obsidian |

---

## Repository Structure

```
docs/
bootstrap/
stacks/
templates/
examples/
scripts/
assets/
```

---

## Documentation Structure

```
Business
Engineering
Operations
Reference
Runbooks
```

---

## Platform Principles

- Git is the source of truth.
- Documentation is part of the platform.
- Infrastructure is reproducible.
- Containers are disposable.
- Persistent data is protected.
- Every change is documented.

---

## Getting Started

Read the documentation in this order:

1. Platform Vision
2. Project Charter
3. Architecture Overview
4. Bootstrap Server
5. Deploy Portainer
6. Deploy Application Stacks

---

## Project Status

**Version:** v0.1.0

**Status:** Foundation