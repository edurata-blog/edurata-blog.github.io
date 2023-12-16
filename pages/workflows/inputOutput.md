---
layout: default
title: Input Output Processing
parent: Workflows
nav_order: 2
---

# Input Output Processing

You can use a few different methods to transport data across steps:

- **Input output config**: By default a json object or in the case of docker runtime a mapping to CMD or ENV variables\* -> good for small data
- **Artefacts**: Files that are uploaded to a S3-Bucket and downloaded in the next step. -> good for intermediate data
- **Cache**: The same as artefacts but instead of going over a S3-Bucket the file is kept in a local Filesystem. -> good for large sized data

| Runtime | Input config | Output config | Artefacts | Cache |
| ------- | :----------: | :-----------: | :-------: | ----: |
| Python  |     yes      |      yes      |    yes    |   yes |
| Nodejs  |     yes      |      yes      |    yes    |   yes |
| Docker  |    yes\*     |      no       |    no     |   yes |
