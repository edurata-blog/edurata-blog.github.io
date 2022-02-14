# 3. Workflows

Workflows are a combination of multiple Functions. They can be ordered in a so-called [Directed Acyclic Graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph) and have input and output similar to functions. They may also be used recursively as a part of another workflow and scheduled to be executed automatically in a cron interval.

## comparison to functions and examples

Functions are written with the goal to serve a single responsibility while being as generic as possible. In turn workflows can be both and it's up to the designer to decide how specific it should be. 

| Attribute | **Function** | **Workflow** |
|---|---|---|
| Has Interface | Yes | Yes |
| Main Purpose | Data Processing | Data Transport |
| Abstraction | Low | High |
| Generality | High | Low |
| Responsibility | Single | Multiple |
| Designed to be | Generic | Specific & Generic |

### A comparison along abstraction and generality

- **Abstraction**: the amount of technicality that is "abstracted" away. Technicality here is anything that has to do with actual processing of data like Databases, programming etc..
- **Generality**: the amount of different use cases it can be applied to.

As a rule of thumb for functions you want high generality (lots of use cases) and low abstraction (specific technology), while it is directly inverse for workflows: low generality (specific use case) and high abstraction (no technical details).

### Examples for good workflows

Examples for good workflows are:

- Onboarding new Employee to Team
- Onboarding new Employee to HR Team (less generic but still okay)
- Change Status of Employee (very generic but still okay)
### Examples for bad workflows

- Employee Action (generality too high)
- Onboarding Mr. Foo to "Infrastructure" Team (generality too low)
- Delete Entry from "Employee" Table (abstraction too low, but still good for function)
- Delete Mr.Foo Row from "Employee" Table (abstraction and generality too low)
## Workflow config

In order to register a workflow into the registry you need to write a config that defines the workflow fully.

```yaml
apiVersion: "0.0.1"
title: convert String
description: Converts any of the supported formats of strings
action: MAP
multiple: true # multiple records can be processed in parallel
interfaces:
  global:
    - name: inputStringFormat
      required: true
      description: The Format of the string(s) to be converted
      enum:
        - utf8
        - hex
        - base64
    - name: outputStringFormat
      description: The Format of the resulting string(s)
      required: true
      enum:
        - utf8
        - hex
        - base64
  input:
    resourceId: charset
    multiple: true
  output:
    resourceId: charset
    multiple: true
```
## Function config
