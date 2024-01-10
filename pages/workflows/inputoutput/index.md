---
layout: default
title: Input Output Processing
parent: Workflows
nav_order: 2
---

# Input Output Processing

You can use a few different methods to transport data across steps:

- **Input output JSON**: By default a json object or in the case of docker runtime a mapping to CMD or ENV variables\* -> good for little data or only configuration.
- **Artefacts**: Files that are uploaded to a S3-Bucket and downloaded in the next step. [Read more](artefacts.md). -> good for files that exceed 256kb in size but are too small to be run through the cache. If the size is higher than 5mb it is recommended to use the cache to be time efficient.
- **Cache**: The same as artefacts but instead of uploading it to an S3-Bucket the file is kept in a local Filesystem. [Read more](./cache.md). -> good for large sized data that would take too long to upload to a S3-Bucket.

## Supported

| Runtime | Input JSON | Output JSON | Artefacts | Cache |
| ------- | :--------: | :---------: | :-------: | ----: |
| Python  |    yes     |     yes     |    yes    |   yes |
| Nodejs  |    yes     |     yes     |    yes    |   yes |
| Docker  |   yes\*    |   yes\*\*   |    no     |   yes |

\* The Input for docker steps can be only done through environment variables or command arguments, which can be configured in the [definition](../registry/definitions/interface.md)
\*\* The json output needs to be passed through the api as documented [here](./outputsApi.md)
