---
title: Architecture Overview
version: 0.1.0
status: Approved
owner: Infrastructure Team
last_updated: 2026-07-09
---

# Architecture Overview

## Purpose

This document describes the high-level architecture of the Container Platform Reference (CPR).

It defines the major platform components, their responsibilities, and how they interact. Detailed implementation procedures are documented separately in the relevant runbooks.

---

# Architecture Principles

The platform is designed around the following principles:

- Git is the source of truth.
- Infrastructure is reproducible.
- Documentation is part of the platform.
- Containers are disposable.
- Persistent data is protected.
- Simplicity is preferred over unnecessary complexity.

---

# Platform Layers

```
Users
   │
   ▼
Applications
   │
   ▼
Shared Services
   │
   ▼
Platform Services
   │
   ▼
Docker Engine
   │
   ▼
Ubuntu Server LTS
   │
   ▼
Hardware
```

Each layer has a defined responsibility and should remain independent from the layers above it.

---

# Layer Responsibilities

## Hardware

Provides the physical resources required to operate the platform.

Examples:

- Physical server
- Virtual machine

---

## Operating System

Ubuntu Server LTS provides the supported operating system.

Responsibilities include:

- Networking
- Storage
- Security updates
- Firewall
- SSH access
- Time synchronization

---

## Container Runtime

Docker Engine provides container execution.

Responsibilities include:

- Container lifecycle
- Networks
- Volumes
- Images
- Docker Compose

Docker Engine is installed directly on Ubuntu and is not managed by Portainer.

---

## Platform Services

Platform Services provide the operational capabilities required by the platform itself.

Examples:

- Portainer
- Reverse Proxy (future)
- Authentication (future)
- Monitoring (future)

These services support the platform rather than business applications.

---

## Shared Services

Shared Services are consumed by multiple applications.

Examples:

- PostgreSQL
- MariaDB
- Redis
- MinIO
- RabbitMQ

Applications should reuse Shared Services whenever practical instead of deploying their own copies.

---

## Applications

Applications deliver business value.

Examples:

- Wiki.js
- Grafana
- Nextcloud
- Gitea
- Uptime Kuma

Applications should remain independent whenever possible.

---

# Deployment Workflow

```
Git Repository
      │
      ▼
Portainer
      │
      ▼
Docker Compose
      │
      ▼
Docker Engine
      │
      ▼
Running Containers
```

Production deployments originate from Git.

Manual configuration changes inside Portainer should be avoided.

---

# Storage Layout

The platform stores runtime data under:

```
/opt/docker
```

Primary directories:

```
/opt/docker
│
├── data/
├── backups/
├── scripts/
├── archive/
└── tmp/
```

Persistent application data is stored using bind mounts under `/opt/docker/data`.

Docker-managed named volumes should only be used where explicitly approved.

---

# Backup Boundary

The following assets are considered critical:

- Application data
- Configuration files
- Compose files
- Environment files
- Scripts
- Documentation repository

Containers and Docker images are not backed up because they are reproducible.

---

# Source of Truth

The platform has two authoritative sources:

| Asset | Source |
|--------|--------|
| Documentation | Git Repository |
| Stack Definitions | Git Repository |

The running server is an implementation of the repository, not the other way around.

---

# Design Goals

The architecture prioritizes:

- Simplicity
- Consistency
- Maintainability
- Recoverability
- Operational clarity

---

# Related Documents

- Platform Vision
- Project Charter
- Documentation Standard
- Bootstrap Server Runbook