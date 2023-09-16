---
layout: default
title: Workflow Definition
parent: Definitions
grand_parent: Registry
nav_order: 2
---

# Workflow config

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
