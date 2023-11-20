---
layout: default
title: Environments
parent: Deployments
nav_order: 5
---

# Environments

An Environment is a namespace/label that can be used to scope and isolate [deployments](index.md). Usually environments describe different deployed versions of a software product with differing importance and usage. Common names for environments are "development", "staging", "preprod", "production", "feature" etc.. but any name is possible.

For example a new version of a workflow `test-workflow` can be first tested in a deployment on i.e. `development` with non-critical data and only later used in a deployment with the environment i.e. `production`.

## Usage with globals

Environments work especially well with [globals](../globals/index.md) like secrets and variables as you can scope them as well by environment and therefore avoid accidentally using critical values in the wrong deployment.
