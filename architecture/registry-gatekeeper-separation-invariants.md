# Registry–Gatekeeper Separation Invariants

## Purpose

The GRC-P governance architecture requires strict separation between the **authority plane** and the **execution enforcement plane**.

This separation prevents systems from silently redefining governance policy or generating unverifiable audit evidence.

The **Registry–Gatekeeper Separation Invariants** define the minimum architectural constraints required to preserve deterministic governance enforcement.

---

## Architectural Roles

### Registry (Authority Plane)

The registry is the **authoritative source of governance state**.

It defines:

- governance checks
- waivers
- revocations
- readiness state
- canonical governance evidence

The registry does not execute operational actions.

---

### Gatekeeper (Enforcement Plane)

The gatekeeper is the **runtime enforcement boundary**.

It intercepts operational requests and enforces permit/deny decisions using registry authority state.

The gatekeeper does not define governance rules.

---

## Separation Invariants

### 1. Authority Ownership

A **Registry MUST be the sole authority** defining governance rules.

A Gatekeeper **MUST NOT create, modify, or interpret governance rules independently of the Registry.**

---

### 2. Enforcement Responsibility

A **Gatekeeper MUST enforce governance decisions** prior to operational execution.

If governance readiness cannot be verified, the gatekeeper **MUST fail closed and deny execution.**

---

### 3. Rule Immutability at Enforcement

A Gatekeeper **MUST treat Registry governance state as authoritative and immutable during evaluation.**

Gatekeepers **MUST NOT override registry rules with local policy.**

---

### 4. Canonical Evidence Authority

The **Registry MUST maintain the canonical governance evidence ledger**.

Gatekeepers MAY maintain local operational telemetry but **MUST NOT treat local records as authoritative governance evidence.**

All canonical governance evidence **MUST be committed to the Registry.**

---

### 5. Enforcement Dependency

A Gatekeeper **MUST require access to Registry governance state in order to evaluate operational readiness.**

If Registry authority state cannot be validated, the gatekeeper **MUST deny execution.**

---

### 6. Identity Independence

The identity of the Gatekeeper **MUST NOT grant authority to define governance state.**

Authority originates exclusively from the Registry.

---

### 7. Execution Isolation

Operational systems **MUST NOT bypass the Gatekeeper to access protected execution paths.**

The Gatekeeper represents the enforcement boundary between governance authority and operational execution.

---

## Security Rationale

These invariants prevent the following failure modes:

- self-authorizing enforcement systems
- silent policy overrides
- unverifiable governance audit trails
- execution systems bypassing governance enforcement
- fragmented governance authority

Maintaining strict separation ensures that governance remains **structural rather than advisory**.

---

## Summary

Under GRC-P:

- **Registry defines governance**
- **Gatekeeper enforces governance**
- **Registry records canonical evidence**

No single component may simultaneously define rules, enforce rules, and record authoritative evidence.

This separation forms the foundation of deterministic governance enforcement.
