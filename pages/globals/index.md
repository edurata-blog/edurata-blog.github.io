---
layout: default
title: Globals
nav_order: 5
has_children: true
---

# Globals (Variables and Secrets)

Variables and Secrets are key value stores that are globally accessible to all workflows. Variables are considered non-sensitive and the value is visible in the UI. Secrets are considered sensitive and cannot be retrieved after saving.

Globals can be used to provide central information to your deployed workflows. Instead of saving the inputs to the workflows at the deployment level you can just link them to the respective variable or secret and thereby avoid copy-paste.

Global secrets are also used to save credentials to authorize third party services like private git repositories, private image repos etc.

# Environments of globals

Variables and secrets can be scoped by an environment. If you don't specify an environment the "default" environment is assigned. Environments on globals results in the following behaviour:

- globals with the "default" environment can be accessed by deployments of all environments
- globals with any other environment (e.g. "prod") can only be accessed by deployments with the same environment (e.g. "prod")
