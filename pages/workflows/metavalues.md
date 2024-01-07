---
layout: default
title: Meta Values
parent: Workflows
nav_order: 1
---

# Meta Values

The following meta values are available for use in the [workflow definition](../registry/definitions/workflowDefinition.md) with the same syntax as dependencies:

- `${meta.deploymentId}`: The deploymentId. Useful for scoping files in the cache.
- `${meta.executionId}`: The executionId. Useful for scoping files in the cache.
- `${meta.workflowId}`: The workflowId. Useful for scoping files in the cache.
- `${meta.cacheMountDir}`: The directory where the cache is mounted.
