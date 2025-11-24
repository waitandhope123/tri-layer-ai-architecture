# System Diagrams

This document contains both the ASCII-based diagram and a rendered flowchart of the Tri-Layer Cooperative AI Oversight Architecture.

---

## 1. ASCII Diagram

           ┌────────────────────────────────────────┐
           │               User Input               │
           └────────────────────────────────────────┘
                            │
                            ▼
              ┌────────────────────────┐
              │      SecondaryAI       │
              │   (Generator/Actor)    │
              └────────────────────────┘
                            │
                     Proposed Solution
                            │
                            ▼
              ┌────────────────────────┐
              │       GuardianAI       │
              │ (Logic/Safety Check)   │
              └────────────────────────┘
                  │              │
                  │ Approved     │ Errors + Fixes
                  ▼              │
             ┌───────────┐       │
             │  Output   │◄──────┘
             └───────────┘
                           
                          (Meanwhile)
                            ▼
              ┌────────────────────────┐
              │     MetaGuardian        │
              │ (Hidden Auditor/Logger) │
              └────────────────────────┘

---

## 2. Mermaid Diagram (Rendered by GitHub)

```mermaid
flowchart TD
    A[User Input] --> B[SecondaryAI<br>(Generator/Actor)]
    B -->|Proposed Solution| C[GuardianAI<br>(Logic/Safety Check)]
    C -->|Errors + Fixes| B
    C -->|Approved| D[Output]
    B -.-> E[MetaGuardian<br>(Hidden Auditor/Logger)]
    C -.-> E
