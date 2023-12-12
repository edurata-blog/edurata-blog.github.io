---
layout: default
title: Interface
parent: Definitions
grand_parent: Registry
nav_order: 3
---

# Interfaces & validation

Both workflow and functions have inputs and outputs. The validation of these inputs and outputs can be defined in an attribute [interface](./configs.md#interface). Validation is used during development and during runtime.

### During creation of a workflow

The interface is used to validate during creation of a workflow if all fields are correct. If input and output values of steps are compatible and if there are loops.

### Runtime validation

Additionally the interface checks for the presence of values in required input values of a step during execution of a deployment. If the required input values are not found, the execution will fail before executing this step.

## How to write an interface

Interfaces are defined in the key `interface`. This key in turn contains two keys `inputs` and `outputs` which each define the interface in the [json schema standard](https://json-schema.org/). Take for example the interface of the function [here](https://github.com/Edurata/edurata-functions/tree/b6284c0f34f51062591d18c5ba1bfb19f72f8906/crud/axios)

```yaml
#...
interface:
  inputs:
    properties:
      url:
        type: string
        description: The url to fetch
      method:
        type: string
        description: The http method
      headers:
        type: object
        description: The http headers
      body:
        type: object
        description: The http body
    required: [url]
  outputs:
    properties:
      response:
        type: object
        properties:
          data:
            type: object
            description: The http response body
          status:
            type: number
            description: The http status code
          statusText:
            type: string
            description: The http status text
          headers:
            type: object
            description: The http response headers
      error:
        type: object
        properties:
          message:
            type: string
            description: The error message
          code:
            type: string
            description: The error code
          config:
            type: object
            description: The http request config
          request:
            type: object
            description: The http request
          response:
            type: object
            description: The http response
          isAxiosError:
            type: boolean
            description: Whether the error is an axios error
    required: [response]
```
