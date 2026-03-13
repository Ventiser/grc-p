# GRC-P
Governance Runtime Control Protocol

![GRC-P Version](https://img.shields.io/badge/GRC--P-v1.0--draft-blue)

GRC-P defines a deterministic governance control plane for automated systems.

The standard separates **governance authority** from **runtime execution**, ensuring that operational actions are evaluated against authoritative governance state before execution occurs.

GRC-P establishes the architectural model for:

- registry authority
- runtime enforcement gatekeepers
- deterministic governance readiness evaluation
- fail-closed operational decisions
- tamper-evident governance evidence

---

## Architecture Overview

The GRC-P architecture separates governance authority from execution systems.


Registry Authority
↓
RGIS Protocol
↓
Gatekeeper Enforcement
↓
Execution Systems


- **Registry Authority** maintains governance state.
- **Gatekeepers** enforce permit/deny decisions before execution.
- **Execution systems** perform actions only when governance readiness is satisfied.

---

## Relationship to RGIS

GRC-P defines the **governance architecture**.

The runtime interoperability protocol used by registry authorities and gatekeepers is defined by **RGIS**.

RGIS repository:

https://github.com/Ventiser/rgis

In simple terms:

- **GRC-P** explains the governance architecture.
- **RGIS** defines the runtime protocol.

---

## Repository Structure


specs/ Formal GRC-P specification
architecture/ Reference architecture documents
foundations/ Mathematical and theoretical foundations


---

## Status

Draft publication of **GRC-P v1.0**.

---

## Stewardship

Maintained by **Ventiser**.
