# Software architecture of storage-trace (r6)

The components of the storage, the interfaces between them, and how they work together. A software
requirement of the storage names in `component` the component that meets it; the requirements are
in [software-requirements.yaml](../requirements/software-requirements.yaml). The document is
written for whoever builds and tests the storage.

## Components

| Component | What it does | Software requirements |
|---|---|---|
| trace | hands the trace by test case, and with each requirement the measures that control it and their hazard or threat | SR_7, SR_12 |
| gaps | marks the places of the trace where a link, a test case, an implementation or a test result is missing, and the hazards and threats without a measure or without a passed test result | SR_1 to SR_5, SR_10, SR_11 |
| verification | counts a passed inspection of the realization of a requirement as its verification | SR_18 |
| maturity | gives the maturity of a requirement, of a group, and of a level, a feature or a release | SR_13 to SR_17 |
| states | counts the states of the requirements, of the tests and of the code, per release and per library | SR_6, SR_8, SR_9 |

## Interfaces

- `StorageSource` (ARC_12 in
  [specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product)) towards the
  reporter: every component hands its answer over it.
- gaps reads the links of trace: a place is missing where trace has no link.
- maturity reads gaps and verification: a step is reached up to the first gap, and a requirement
  whose method is inspection is verified by its passed inspection.

## How they work together

trace holds the links of the trace. gaps marks where a link is missing, and verification says
which requirements an inspection verifies. maturity counts from both how far each requirement has
come. states counts the states of the objects apart from the links.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-24 | - | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
