# System Diagrams

This document provides conceptual diagrams illustrating the data flow and role separation in the **Tri-Layer Cooperative AI Oversight Architecture**.

These diagrams are illustrative only and do not imply implementation details.

---

## 1. ASCII Diagram (Conceptual)

           ┌────────────────────────────────────────┐
           │               User Input               │
           └────────────────────────────────────────┘
                            │
                            ▼
              ┌────────────────────────┐
              │      SecondaryAI       │
              │   (Generator / Actor)  │
              └────────────────────────┘
                            │
                     Proposed Solution
                            │
                            ▼
              ┌────────────────────────┐
              │       GuardianAI       │
              │ (Evaluator / Validator)│
              └────────────────────────┘
                  │              │
                  │ Approved     │ Errors + Feedback
                  ▼              │
             ┌───────────┐       │
             │  Output   │◄──────┘
             └───────────┘

        [MetaGuardian observes all interactions out-of-band]

              ┌────────────────────────┐
              │     MetaGuardian        │
              │ (Governance Auditor)    │
              └────────────────────────┘

MetaGuardian does not participate in runtime decision-making.
Its outputs are intended for external governance and operational workflows.

## 2. Rendered Flowchart (Mermaid)
flowchart TD
    A["User Input"] --> B["SecondaryAI<br/>(Generator / Actor)"]
    B -->|Proposed Solution| C["GuardianAI<br/>(Evaluator / Validator)"]
    C -->|Errors + Feedback| B
    C -->|Approved| D["Output"]

    B -.-> E["MetaGuardian<br/>(Out-of-Band Auditor)"]
    C -.-> E
