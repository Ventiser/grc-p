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
RGIS
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

- **GRC-P** defines the governance architecture.
- **RGIS** defines the runtime interoperability protocol used by registry authorities and gatekeepers operating under GRC-P.

---

## Repository Structure


specs/ Formal GRC-P specification
architecture/ Reference architecture documents
foundations/ Mathematical and theoretical foundations


---

## Status

Draft publication of **GRC-P v1.0**.

---

## Related Repositories

The GRC-P architecture is implemented through a set of complementary repositories representing the architecture, protocol, and reference implementations.

GRC-P — Governance architecture  
https://github.com/Ventiser/grc-p

RGIS — Registry–Gatekeeper protocol  
https://github.com/Ventiser/rgis

GovenAI Registry — reference registry authority implementation  
https://github.com/Ventiser/govenai-registry

JobQue Gatekeeper — reference runtime enforcement implementation  
https://github.com/Ventiser/jobque-gatekeeper

---

## Intellectual Property

Certain concepts described in this repository may be covered by pending patent applications owned by Ventiser Pty Limited.

See `PATENT-NOTICE.md` for additional details.

---

## Stewardship

Maintained by **Ventiser**.
