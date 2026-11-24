# Software architecture of mcp-trace (r6)

The components of the MCP server, the interfaces between them, and how they work together. A
software requirement of the MCP server names in `component` the component that meets it; the
requirements are in [software-requirements.yaml](../requirements/software-requirements.yaml). The
document is written for whoever builds and tests the MCP server.

## Components

| Component | What it does | Software requirements |
|---|---|---|
| tools | offers an assistant one tool per view of the viewer | SR_1 |
| requests | sends what the assistant asks for to the reporter, with the scope, the level, the narrowings and the process reference model | SR_6 to SR_12, SR_16 |
| answers | hands the assistant what the reporter answers, shortened to the rows asked for, with the view and the filters that show the same, and the reason of a refusal | SR_2 to SR_5, SR_13, SR_15 |
| operation | starts from a release with no setting other than those its operator manual names | SR_14 |

## Interfaces

- the Model Context Protocol (ARC_52 in [specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product)) towards an assistant: tools offers its tools over it,
  and answers hands the answers.
- the REST API (ARC_11) towards the reporter: requests asks over it.
- tools hands requests what the assistant asks for; requests hands answers what the reporter
  answers.

## How they work together

An assistant calls a tool. requests turns the call into a request to the reporter, and answers
turns the answer of the reporter into the answer of the tool. operation starts the server.

## Change history

| Version | Date | Change | Reason | By |
|---|---|---|---|---|
| 1.1.1 | 2026-11-24 | - | #34 | Claude Opus 5.5, author; Mathias Fischer, reviewer |
