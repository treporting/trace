# Software requirements of mcp-trace (r5)

What the MCP server has to do, each requirement one behaviour that a test can verify. A
requirement names as uplink a system requirement (r2) or a requirement of the architecture (r3)
allocated to the MCP server (ARC_51), to its interface towards an assistant, the Model Context
Protocol (ARC_52), or to its interface towards the reporter, the REST API (ARC_11). These lie in
[specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product), in
`architecture/system-architecture.yaml`. The document is written for whoever builds and tests the
MCP server.

The requirements themselves - ids `SR_n` - are in
[software-requirements.yaml](software-requirements.yaml), in the format of
[formats.md](https://github.com/treporting/specs-and-deploy-process/blob/main/formats.md); this file
holds what explains them.

## Allocated, with no software requirement of its own

- ARC_27: the same API from every mode of operation is the reporter's to keep.
- ARC_36: the format of an answer; the MCP server asks the reporter always in the same one.

## Two software requirements from one uplink

- ARC_54 asks two behaviours: SR_15 answers at most as many rows as the assistant names, SR_3
  says how many rows it left out.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-22 | - | #10 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
