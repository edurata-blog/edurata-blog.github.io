# 3. Workflows

Workflows are a combination of Functions and other Workflows. They can be ordered in a so-called [Directed Acyclic Graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph) and like Functions have an interface (inputs and outputs). They can be invoked on a regular basis or by api calls through [Triggers](https://google.com)

## Workflow config

They may also be used recursively as a part of another workflow and scheduled to be executed automatically in a cron interval.

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
