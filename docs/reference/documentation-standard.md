---
title: Documentation Standard
version: 0.1.0
status: Approved
owner: Infrastructure Team
last_updated: 2026-07-09
---

# Documentation Standard

## Purpose

This document defines the documentation standards for the Container Platform Reference (CPR).

The objective is to ensure that all documentation is consistent, accurate, maintainable, and version-controlled.

---

# Documentation Principles

Documentation is considered part of the platform.

Every platform change must be accompanied by the corresponding documentation update.

Documentation should always describe the approved implementation, not every possible implementation.

---

# General Principles

Documentation must be:

- Accurate
- Concise
- Consistent
- Version controlled
- Reviewed
- Tested

Avoid opinionated language unless documenting an approved platform standard.

---

# Writing Style

Documentation should be written using:

- Present tense
- Active voice
- Professional language
- Technical accuracy

Prefer:

> Configure UFW to allow SSH access.

Instead of:

> You should probably configure the firewall.

---

# Document Structure

Every document should begin with front matter.

Example:

```yaml
---
title:
version:
status:
owner:
last_updated:
---
```

Every document should contain a top-level heading matching the document title.

---

# Headings

Use heading levels consistently.

```
# Document Title

## Section

### Subsection
```

Do not skip heading levels.

---

# File Naming

Use lowercase filenames.

Use hyphens instead of spaces.

Examples:

```
architecture-overview.md
bootstrap-server.md
deploy-stack.md
```

Avoid:

```
Architecture.md
Docker Setup.md
MyDocument.md
```

---

# Code Blocks

Always specify the language when possible.

Example:

````text
```bash
docker compose up -d
```