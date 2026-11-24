# Software requirements of viewer-trace (r5)

What the viewer has to do, each requirement one behaviour that a test can verify. A requirement
names as uplink a requirement of the architecture (r3) on the viewer (ARC_1). These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests the
viewer.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them.

## Two uplinks

- SR_1 serves ARC_225 and ARC_278: the head of the trace and the names of its levels come from the
  reporter, also those that the configuration of a customer sets.
- SR_21 serves ARC_233 and ARC_270: how many objects a narrowing left out, as the reporter answers
  it (SR_27 of the reporter).

## Open

- ARC_243, ARC_255 and ARC_258 are still `draft`, as their system requirements SYS_27, SYS_57 and
  SYS_64 are.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-21 | - | #8 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
| 2.1.1 | 2026-11-24 | Uplinks: the requirements of the architecture on the viewer; sections on allocation removed | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
