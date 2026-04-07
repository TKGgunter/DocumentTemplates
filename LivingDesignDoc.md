# Design Doc metadata:

visibility: <(public|confidential)>
author(s): <single author or List sorted alphabetically>
tags: <list of tags>
**Change History** (This could be replaced by github for doc reviews)
Table of Date and Summary of Major change and who reviewed.

> [!WARNING] Warning
> What is the point of this doc?

# Title
The Title should set expectations for the document. It should provide
the topic of discussion. Its phasing should be considered to elicit buy in.


## Outline
- Background and Motivation
- High/Low Level Design
    > Because this is a living document include each draft revision sequentially.
    > Simply adding a `draft #` tag before the code/diagram is sufficient.
    - High level diagrams
    - Low level code
- Interfaces
- Configurations and Statistics
- Limitations Risks
- Tests and Results
- Opens and Future features
- Implementation

## Introduction
The introduction should frame the document. It should provide high level
context, provide a reason for why the document exists, the problem the document
is trying to solve. Lastly this section should tell the reader what to expect
from the document and make requests of the reader.

## Context/Problem statement
Some times a dedicated section is needed to properly contextualize the problem.
The nature of this section depends on the specifics of the document. 

## <Body>

---
Something from other team member:
-Opens with context/history, then makes a clear case for why the status quo is insufficient
- Uses a direct, opinionated tone -- "this has been abused", "for hothering" ...
- Structures with clear problem statement -> background -> proposed solution -> implications
- explains the "why" deeply before the "what"
- uses inline technical detail but always ties it back to operational impact
- uses faq sections for anticipated pushback
- calls out past technical debt
