# How to write a runbook

This article contains a collection of notes which may be useful when writing
runbooks. It is organized as a template, from which the reader should be able
to copy and pasted in needed detail.

## Alarms

```
# <Alarm Title>
## Definition
<Alarm code link> as of <date written>.
**Metric:** <Metric Name>
**Alarm Threshold:** <{gt|lt|eq} # Value>
<Describe the intent of the alarm, what it means for the service and how it impacts customers.>

## Remediation
<Provide a step by step guide to investigating and addressing the issue.>

"""
Example:
1. Resource Creation
    1. Create AWS regional count
        1. ...
...
1. 
"""
```
> **Ideas for the future:**
> I would love to keep everything in one place. If the alarms runbook were to be generated from the code that creates the 
> alarms it might be more likely that the documentation stays up to date. A potential benefit of "localization".


## Service Spin up
```
# <??>

```
