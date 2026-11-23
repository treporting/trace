# Software requirements of storage-trace (r5)

What the storage has to do, each requirement one behaviour that a test can verify. A requirement
names as uplink one requirement of the architecture (r3) on the storage (ARC_3), most of them over
`StorageSource` (ARC_12) towards the reporter. These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests the
storage.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them. The field `component` groups them by the part of the storage that
realizes them, such as `gaps`, `states` or `maturity`.

## From the reporter

SR_1 to SR_18 stood with the reporter before: the storage builds the trace, marks its gaps, counts
the states, finds the levels a requirement is verified on, traces the hazards and gives the
maturity; the reporter answers what the storage hands. Their old keys in the reporter are
obsolete:

| Storage | Reporter, obsolete |
|---|---|
| SR_1 to SR_5 | SR_6 to SR_10 |
| SR_6 | SR_13 |
| SR_7 | SR_14 |
| SR_8, SR_9 | SR_16, SR_17 |
| SR_10 to SR_12 | SR_32 to SR_34 |
| SR_13 to SR_16 | SR_81 to SR_84 |
| SR_17 | SR_86 |
| SR_18 | SR_107 |

## Open

`<empty>`

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-24 | - | #24 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
