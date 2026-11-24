# Software requirements of reporter-trace (r5)

What the reporter has to do, each requirement one behaviour that a test can verify. A requirement
names as uplink one requirement of the architecture (r3) on the reporter (ARC_2), most of them over
the REST API (ARC_11) towards the viewer and the MCP server, two over the identity of a user
(ARC_17). These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests the
reporter.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them. The field `component` groups them by the part of the reporter that
realizes them, such as `trace`, `filters` or `maturity`.

## Open

- ARC_179 and ARC_201 are still `draft`, as their system requirements SYS_27 and SYS_64 are.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-21 | - | #2 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
| 2.1.1 | 2026-11-24 | Uplinks: the requirements of the architecture on the reporter; sections on allocation removed | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
