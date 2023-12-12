---
layout: default
title: Workflow Sources
parent: Sources
grand_parent: Registry
nav_order: 1
---

# Workflow sources

A Source of a workflow is defined in a deployment in order for the deployment to know which workflow to deploy. The source can be either a reference to a git commit or a reference to a registry item.

{: .info}
Currently nested workflows don't work. So it is not yet possible to define workflows as source in a step for another workflow, only functions.

## Registry

The source of a workflow can point directly to an entry in the registry if it was already created before.

- name: The name of the workflow in the registry
- revision: The revision of the workflow in the registry

## Git

Git source is practical if you are still in development and need to do fast updates.

- **repoUrl**: The repository url
- **path**: The path inside the repository to the `.eduwc.yml` (can have any prefix in front and both yaml notations, i.e. `foo.eduwc.yml` or `bar.eduwc.yaml`)
- **ref**: The branch, or commit hash that you want to target. Defaults to the default branch

{: .info }
If the deployment detects changes (there is a newer git commit than the deployed one) it will automatically create a new workflow version in the registry. If a previous version with the same `ref` is present it will automatically select that one.

{: .info }
The name for the workflow will either be taken from `.eduwc.yml` if specified or fall back to a combination of repoUrl, path and ref of the source.

{: .warning }
If you use a default branch or tag as `ref` in a deployment or workflow and push another commit to it, the changes will not be deployed automatically. In this case you need to additionally retrigger the deployment.

### Private Git repositories

If you need to target a private repository you need to create a [Secret](../../globals/secrets.md) with the `repoUrl` as name, type as repository and value as access token.
