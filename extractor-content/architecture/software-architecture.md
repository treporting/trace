# Software architecture of extractor-content (r6)

The components of extractor-content, the interfaces between them, and how they work together. A
software requirement of extractor-content names in `component` the component that meets it; the
requirements are in [software-requirements.yaml](../requirements/software-requirements.yaml). The
document is written for whoever builds and tests extractor-content.

## Components

| Component | What it does | Software requirements |
|---|---|---|
| configuration | takes the configuration, the releases of the libraries and the mapping of the fields | SR_1 to SR_4 |
| plug-ins | starts a package for each kind of content, hands it the files of its kind in their baseline, and makes the links once a baseline is complete | SR_5 to SR_8 |
| requirements | hands every requirement read | SR_9 |
| tests | hands every test case, test procedure and test result read | SR_10 |
| code | hands every piece of code that names the requirements it implements | SR_11 |
| links | hands every link read with its two ends | SR_12 |
| work products | hands each file read as a work product | SR_13 |
| reviews | hands the status, the reviews and the findings of the customer per work product | SR_14 to SR_16 |
| as read | hands every value as the file holds it, with its mapped (`M`) and intermediate (`I`) value | SR_17, SR_18, SR_24, SR_25 |
| integrity | names what it could not read, counts what it read and refused, and hands its errors and warnings; the same files give the same information | SR_19 to SR_22 |
| performance | extracts a data set of size large within the time given | SR_23 |

## Interfaces

- the configuration (ARC_20 in [specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product)) from the customer: configuration reads it.
- the information (ARC_16) towards the storage: requirements, tests, code, links, work products and
  reviews hand over it.
- configuration hands plug-ins the configuration and as read the mapping; plug-ins hands each
  package the files of its kind; as read derives the values every package hands; integrity counts
  what every package read and refused.

## How they work together

configuration reads the configuration. plug-ins starts the packages and hands them the files
baseline by baseline. Each package - requirements, tests, code, links, work products and reviews -
reads its kind of object; as read gives every value its mapped and intermediate form, and integrity
keeps count of what was read and what was not.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-24 | - | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
