# Software architecture of viewer-trace (r6)

The components of the viewer, the interfaces between them, and how they work together. A software
requirement of the viewer names in `component` the component that meets it; the requirements are
in [software-requirements.yaml](../requirements/software-requirements.yaml). The document is
written for whoever builds and tests the viewer.

## Components

| Component | What it does | Software requirements |
|---|---|---|
| filters | lets the user choose the scope, the level, the narrowings and the process reference model, sends them with every request, and shows the filters in effect | SR_2 to SR_5, SR_11, SR_15 to SR_24, SR_27, SR_30, SR_33, SR_34 |
| tables | shows the answers of the reporter as tables | SR_1, SR_6 to SR_9, SR_13, SR_14, SR_28, SR_29, SR_31, SR_35, SR_38, SR_40, SR_71 to SR_74 |
| charts | shows counted states as charts, narrowed and counted exactly as the table beside them | SR_10, SR_12, SR_25, SR_26, SR_32, SR_36, SR_39, SR_59, SR_60 |
| baselines | shows what changed between two baselines | SR_37 |
| export | hands out tables, charts and reports | SR_46 to SR_51 |
| provenance | shows the versions, the data set and its completeness, and a value unknown as unknown | SR_41 to SR_45, SR_69 |
| status | shows that a view is loading, not available or refused | SR_54 to SR_57 |
| navigation | leads from the first screen to every view and back, and links a view with its narrowing | SR_52, SR_53, SR_58 |
| access | shows a user only the views their role grants | SR_64, SR_65 |
| licence | shows the features licensed and the reason of a refusal for a missing licence | SR_66, SR_67 |
| operation | starts from a release and records its errors and warnings | SR_62, SR_63 |
| performance | shows a view of a data set of size large within its share of the time given | SR_61 |
| pages | names on the demo where a vulnerability is reported | SR_68 |
| delivery | carries the licence texts and notices of its components | SR_70 |

## Interfaces

- the REST API (ARC_11 in [specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product)) towards the reporter: filters sends the requests over it, and tables,
  charts, baselines, provenance, status and licence show what it answers.
- filters hands tables, charts and baselines the narrowing they show; charts opens from a part of a
  chart the table of its objects; export takes the tables and charts chosen.

## How they work together

The user chooses in filters what to see. tables and charts show what the reporter answers for it,
provenance and status say what the answer rests on and whether it came, and export hands it out.
access decides which views a user sees at all.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-24 | - | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
