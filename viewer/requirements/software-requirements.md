# Software requirements of viewer-trace (r5)

What the viewer has to do, each requirement one behaviour that a test can verify. A requirement
names as uplink a system requirement (r2) or a requirement of the architecture (r3) allocated to
the viewer (ARC_1) or to its interface towards the reporter, the REST API (ARC_11). These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests the
viewer.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them.

## Allocated, with no software requirement of its own

- ARC_27: the same API from every mode of operation is the reporter's to keep.
- ARC_36: the format of an answer is asked by the export, which names SYS_31.
- SYS_14: realized through the choice of the process reference model of ARC_30 (SR_33).
- SYS_29: realized through the reason of a refusal of ARC_37, which the viewer shows (SR_57).

## Two uplinks

- SR_1 serves SYS_1 and SYS_94: the head of the trace and the names of its levels come from the
  reporter, also those that the configuration of a customer sets.
- SR_21 serves SYS_9 and SYS_83: how many objects a narrowing left out, as the reporter answers it
  (SR_27 of the reporter).

## Not yet derived

- SYS_27, SYS_57 and SYS_64 are still `draft`.
- The interface identity (ARC_17) has no requirements yet. SR_64 names SYS_39 as its uplink
  directly, until it has them.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-21 | - | #8 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
