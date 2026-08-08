# MB-100 — System Architecture

> **The system architecture of the Madina Barakasi Platform**

---

## Document Information

| Field          | Value                  |
| -------------- | ---------------------- |
| Document ID    | MB-100                 |
| Volume         | II — Architecture      |
| Title          | System Architecture    |
| Version        | 0.1.0                  |
| Status         | Draft                  |
| Classification | Canonical              |
| Language       | English                |
| Owner          | Architecture           |
| Created        | 2026-08-08             |
| Last Updated   | 2026-08-08             |

---

# 1. Purpose

MB-100 defines the high-level system architecture of the Madina Barakasi Platform ecosystem.

It establishes the principal repositories, architectural layers, responsibilities, dependency direction, and boundaries between reusable platform capabilities and application-specific business logic.

This document provides the architectural foundation for subsequent engineering decisions.

---

# 2. Architectural Scope

The architecture covers the following principal repositories and systems:

- `madina-platform`
- `madina-crm`
- `madina-barakasi-docs`
- `madina-arabic`

The platform architecture must preserve clear boundaries between technical infrastructure, business applications, and documentation.

---

# 3. Repository Responsibilities

## 3.1 madina-platform

`madina-platform` is the shared technical platform.

Its purpose is to provide reusable technical capabilities for applications in the Madina Barakasi ecosystem.

The current platform structure contains:

```text
packages/
├── ai/
├── api/
├── auth/
├── config/
├── core/
├── database/
├── notifications/
├── shared/
└── ui/