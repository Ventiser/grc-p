# GRC-P Reference Architecture

The GRC-P architecture separates governance authority from execution environments.

Architecture layers:

Authority Layer
    Registry Authority (e.g. GovenAI)

Enforcement Layer
    Gatekeepers (e.g. JobQue)

Execution Layer
    APIs, agents, and operational systems

Gatekeepers consult registry authorities using the RGIS protocol before allowing execution.
