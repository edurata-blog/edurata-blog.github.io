# Introduction

Edurata is BI-Platform enabling users to run `node.js`, `python` and `bash` code in a modular way in the cloud without having to learn Devops.

### You don't need to care about:

- Cloud Providers (AWS, Google Cloud, Azure, etc..)
- Orchestration (Docker & Kubernetes)
- Scaling
- Availability
- Interfaces & Apis
                                                                            |

### Use cases:

- CI/CD pipeline
- BI Ingest pipelines
- Cron Jobs
- API Backend


# Resources

There is two main resources in this app, [Workflows](https://docs.edurata.com/pages/workflows.html) and [Functions](https://docs.edurata.com/pages/workflows.html).

While **Functions define how** functionality is executed and what information they consume and expose, **Workflows define in which order** Functions are executed and how information flows between them.

## Config files

Both Functions and Workflows are defined through config files. These config files are written in `yaml` and should ideally be hosted in a git repository ([Github](https://github.com/), [Gitlab](https://gitlab.com/), [Bitbucket](https://bitbucket.org/)).

Config files always have a basic structure like the following:

```yaml
apiVersion: "0.0.1" 
title: Example Function or Workflow
description: Anything to explain what's going on
interface: 
    inputs:
        ...
    outputs:
        ...
steps: # This only exists in the Workflow config file
    ...
```
- The *apiVersion* field defines which schema to use for this config file, defaults to the latest.
- The *interface* is used to define what information and in which type is allowed to enter or leave Functions or Workflows.
- The *steps* field only exists in Workflows. It describes the order of how to execute functions 

Any of these config files can also be configured through the [User Interface](https://docs.edurata.com/pages/workflows.html) which also provides intelligent lookups and validation. However in the end only a valid `yaml` file will be used to create and update Workflows and Functions.

Learn more about [Workflows](https://docs.edurata.com/pages/workflows.html) and [Functions](https://docs.edurata.com/pages/workflows.html)


## The interface