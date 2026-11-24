# Software architecture of reporter-trace (r6)

The components of the reporter, the interfaces between them, and how they work together. A software
requirement of the reporter names in `component` the component that meets it; the requirements are
in [software-requirements.yaml](../requirements/software-requirements.yaml). The document is
written for whoever builds and tests the reporter.

## Components

| Component | What it does | Software requirements |
|---|---|---|
| source | reads the data set in one mode - a database server, a database run with it, a data file or data generated in memory - and answers the same in each | SR_56 to SR_61 |
| filters | takes the scope and the narrowings of a request, carries the attributes down the trace, and answers what to choose from and what the narrowing left out | SR_19 to SR_31, SR_108 |
| trace | answers the trace from the level asked for, and the requirements without a passed test result, an implementation or a test case | SR_1 to SR_5, SR_11, SR_15 |
| states | counts the states of the objects the trace answers, from their mapped value | SR_18, SR_99, SR_100 |
| features | answers one row per feature with its counted states | SR_12 |
| maturity | takes the chain and answers the maturity grouped by feature | SR_85, SR_87 to SR_89 |
| process | names the levels as the process reference model asked for, or as the configuration of a customer sets them | SR_38 to SR_41 |
| compliance | answers per clause of a standard the requirements that address it and its state | SR_35 to SR_37 |
| verification | answers the verification method, the reviews of a work product and the findings of the customer | SR_103 to SR_106 |
| baselines | answers the work products, the releases and libraries, and what changed between two baselines | SR_42 to SR_45 |
| structure | answers the subsystems, components and units of a project, and narrows the code to them | SR_46, SR_47 |
| plausibility | analyses a data set against the rules of plausibility | SR_101, SR_102 |
| provenance | answers its revision, its data set and its completeness, a value unknown as unknown, and the same answer for the same data set | SR_48 to SR_55 |
| export | answers tables as JSON or CSV, and makes reports | SR_69 to SR_73 |
| refusals | refuses a request it cannot answer, with the reason | SR_62 to SR_65 |
| access | answers a request only for an identified user and only what their role grants | SR_74 to SR_77 |
| audit | records reports and what users did | SR_78 to SR_80 |
| licence | checks the licence of a feature and answers which are licensed | SR_95, SR_96 |
| server | answers a data set of size large within the time, memory and users given | SR_90 to SR_94 |
| operation | answers that it runs, records errors and warnings, and starts from a release | SR_66 to SR_68 |
| delivery | answers its version of treporting and carries the licence texts and notices of its components | SR_97, SR_98 |

## Interfaces

- the REST API (ARC_11 in [specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product)) towards the viewer and the MCP server: every component that answers
  answers over it.
- `StorageSource` (ARC_12) towards the storage: source reads the data set over it.
- the identity of a user (ARC_17): access takes it with every request.
- refusals, access and licence check a request before the other components answer it; filters
  hands trace, states, features, maturity, compliance and baselines the scope and the narrowing;
  process hands trace and maturity the levels; states, features and maturity count the rows of
  trace.

## How they work together

A request passes refusals, access and licence first. filters sets its scope and narrowing, process
its levels, and source reads the data set. trace answers the rows; states, features and maturity
count them; provenance says what the answer rests on, and export hands it out as a table or a
report. audit records what was reported and by whom.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-24 | - | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
