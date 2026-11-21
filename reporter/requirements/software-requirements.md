# Software requirements of reporter-trace (r5)

What the reporter has to do, each requirement one behaviour that a test can verify. A requirement
names as uplink one system requirement (r2) or one requirement of the architecture (r3) allocated
to the reporter (ARC_2) or to one of its interfaces: the REST API (ARC_11) towards the viewer and
the MCP server, and `StorageSource` (ARC_12) towards the storage. These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests the
reporter.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them. The field `component` groups them by the part of the reporter that
realizes them, such as `trace`, `filters` or `maturity`.

## Allocated, with no software requirement of its own

- ARC_38 to ARC_49, on `StorageSource`: what the storage hands the reporter. They are realized by
  the storage, not by the reporter.
- SYS_20: realized through the modes of operation, ARC_23 to ARC_28 (SR_56 to SR_61).
- SYS_29 and SYS_34: realized through the refusals of ARC_37 (SR_62 to SR_65).
- SYS_31: the export as CSV is ARC_36 (SR_69); the picture of a chart is the viewer's.

## Not yet derived

- SYS_27 and SYS_64 are still `draft`.
- The interfaces identity (ARC_17) and audit trail (ARC_18) have no requirements yet. SR_74 to
  SR_80 name SYS_39, SYS_40, SYS_43, SYS_44, SYS_88 and SYS_90 as their uplinks directly, until
  those interfaces have them.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-21 | - | #2 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
