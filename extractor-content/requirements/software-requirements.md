# Software requirements of extractor-content (r5)

What extractor-content has to do, each requirement one behaviour that a test can verify. A
requirement names as uplink one requirement of the architecture (r3) on extractor-content (ARC_5),
most of them over the information towards the storage (ARC_16) or the configuration of the
customer (ARC_20). These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests
extractor-content.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-22 | - | #16 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
| 2.1.1 | 2026-11-24 | Uplinks: the requirements of the architecture on extractor-content; sections on allocation removed | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
