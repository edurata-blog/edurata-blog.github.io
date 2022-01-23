# Edurata docs

There is two primary resources that you define in order to setup workflows in your account
## Workflow config

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
