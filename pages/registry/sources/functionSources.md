---
layout: default
title: Function Sources
parent: Sources
grand_parent: Registry
nav_order: 1
---

# Function sources

## Direct

## Git

Git source is practical if you are still in development and need to do fast updates.

- **repoUrl**: The repository url
- **path**: The path inside the repository to the `.edufc.yml`
- **ref**: The branch, or commit hash that you want to target. Defaults to the default branch

{: .info }
Git source will automatically create a new function if it is not present and automatically a new function version if a version is not present with the same definition. If another version with the same name and definition is present it will automatically select that one. The name will either be taken from `.edufc.yml` if specified or fall back to a combination of repoUrl, path and ref of the source.

{: .warning }
If you target branches in a function that is deployed, further updates will not be automatically be deployed. In this case you need to retrigger the deployment.

### Private Git repositories

If you need to target a private repository you need to create a [Secret](../../globals/secrets.md) with the `repoUrl` as name, type as repository and value as access token.

## Image Repo

You can target an image repo as source if you want to run a whole image instead of just code.

- **imageRepoUrl**: The repository Url
- **tag**: The tag of the image Repo
