# Annotation operations and Sky Forge R&D

## Human-supervised annotation workflow

Eric asked AI agents to build and refine this workflow, directed fixes when behavior failed, and owned requirements, QC and acceptance. The annotation manager divides work into bounded pole assignments for engineer bots. Each assignment needs identity evidence, the applicable rules, job-specific exceptions and a stop condition. The manager troubleshoots genuine blockers, takes over only as needed, then hands the pole back rather than becoming the permanent annotator. (Based on private agent work histories and coordination records.)

```mermaid
flowchart TD
  M[Annotation manager] --> A[Assign bounded pole and applicable rules]
  A --> E[Engineer verifies identity and existing state]
  E --> C[Computer-use annotation]
  C --> S[Save and verify persistence]
  S --> Q[Manager quality check]
  Q -->|Complete| N[Next explicit assignment]
  C -->|Blocked| B[Blocker evidence]
  B --> T[Manager troubleshooting or bounded takeover]
  T --> H[Handoff back to engineer]
  H --> S
  Q --> F[QC lead feedback]
  F --> D[Classify measurement, wording, rule gap or uncertainty]
  D --> R[Domain decision plus regression case]
```

## Computer-use operation

Agents operate the annotation UI under human review; uncertain or blocked work goes to a person rather than being guessed.

## QC-reviewed job example

A QC lead edited measurements and note wording on a reviewed job. The comparison separated four things: unchanged output, output explained by a measurement correction, wording-only differences, and substantive rule disagreements. A reviewed example exposed an output-scope error; independent review rejected incomplete corrections. Proprietary rule behavior is withheld.

## Sky Forge R&D workflow

```mermaid
flowchart LR
  A[Authorized evidence] --> P[Provenance and human label review]
  P --> E[Annotation experiments]
  E --> V[Job-separated evaluation]
  V --> Q[Precision and human acceptance gates]
```

A separate read-only preview was observed behind an access gateway; it is not an autonomous production annotator. Internal capture, feature construction and geometry algorithms stay private. Permission, provenance, retention and untouched test jobs remain essential controls.
