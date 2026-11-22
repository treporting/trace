# Software requirements of extractor-content (r5)

What extractor-content has to do, each requirement one behaviour that a test can verify. A
requirement names as uplink a system requirement (r2) or a requirement of the architecture (r3)
allocated to extractor-content (ARC_5) or to one of its interfaces: the files from the extractor of
the system (ARC_15), the information towards the storage (ARC_16) and the configuration of the
customer (ARC_20). These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests
extractor-content.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them.

## Allocated, with no software requirement of its own

- ARC_73 to ARC_77, on the import (ARC_13): what the storage does with what it is handed; they are
  realized by the storage.
- ARC_57 to ARC_61, on the system access (ARC_14): the extractor of the system's.
- ARC_62 to ARC_64 are on the sender, the extractor of the system; SR_6 to SR_8 are the receiving
  side.
- SYS_2, SYS_7, SYS_8, SYS_12, SYS_15, SYS_17, SYS_23, SYS_28, SYS_38, SYS_72 and SYS_74: realized
  through the requirements of ARC_15, ARC_16 and ARC_20 that name them.

## Uplinks straight to a system requirement

- SR_3 (SYS_38): a library in no release is an error; ARC_79 says only that the configuration
  names the libraries of a release.
- SR_4 (SYS_22): the mapping inside extractor-content; ARC_20 has no requirement on it, its contract
  is the mapping of attributes and of values.
- SR_21 (SYS_24) and SR_23 (SYS_53): the share of extractor-content; ARC_74 and ARC_77 are the
  storage's.

## Not yet derived

- SYS_27 and SYS_64 are still `draft`.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-22 | - | #16 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
