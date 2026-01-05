# How to write a runbook

This article contains a collection of notes on writing
runbooks. It is organized as a template, from which the reader should be able
to copy and pasted in needed details.

## Alarms

```
# <Alarm Title>
## Definition
<Alarm code link> as of <date written>.
**Metric:** <Metric Name>
**Alarm Threshold:** <{gt|lt|eq} # Value>
**Example Link:** <link>
<Describe the intent of the alarm, what it means for the service and how it impacts customers. Be brief. Oncalls want context and the ability to determine priority not a novella. >

## Remediation
<Provide a step by step guide to investigating and addressing the issue.>

"""
Example:
1. Resource Creation
    1. Create AWS regional count
        1. ...
...

## Context
<details>
< Provide historical context here. This can be as long and verbose as you would like. This is ok because it's hidden.>    
</details>
"""
```
Alarms are important indicators of service failure. It is important to be able to move quickly and address the service impact when an alarm is triggered. To do so Alarm runbooks must be clear and too the point.


> **Ideas for the future:**
> I would love to keep everything in one place. If the alarms runbook were
> generated from the code that creates the alarms it might be more likely that
> the documentation stays up to date. A potential benefit of "localization".


## Service Spin up
```
# <Step Name>
< high level description what will be accomplish during the step. Just enough to provide context, no more>
1. List each sub step summary, in a one sentence summary.
    > Provide detailed specifics, like bash commands, links, images, and diagrams.
```
