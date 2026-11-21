# trace

The code of the subsystems of treporting, the product: each subsystem is a folder of this repo,
such as `reporter` for reporter-trace, with its software requirements, its tests and its code. It
is written for whoever specifies, reviews or builds a subsystem, and for the auditor who looks for
the evidence.

| File | What |
|---|---|
| [reviews/](reviews/) | the criteria of the documents, and the result of every review made in this repo |
| [documents.yaml](documents.yaml) | every Markdown file, with its version and status |
| [kinds.yaml](kinds.yaml) | the kinds of files: code, read for annotations, and no code |

Two repos lie above. [specs-and-deploy-product](https://github.com/treporting/specs-and-deploy-product)
holds the system requirements and the architecture that the software requirements of a subsystem
name as uplinks. [specs-and-deploy-process](https://github.com/treporting/specs-and-deploy-process)
holds the rules of the work, the formats and the schemas. The tools that check this repo lie in
[tools](https://github.com/treporting/tools); its CI runs them against both.
