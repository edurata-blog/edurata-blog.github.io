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

## Allowed types

Types can be of the typical primitives:

- **boolean**
- **string**
- **float**
- **int**

and the complex types:

- **array**
  - needs another key `items`
- **object**
  - needs another key `properties`

and a few special types that configure how the value is used in the input / output

- **file**
  - expects a string which represents a filepath
  - if a filepath is passed to this property as an output it will try to upload the file at that path and download if passed as an input. [See](../../workflows/artefacts.md)
- **env**
  - expects a string
  - will be passed as environment variable
- **cmdValue**
  - expects a string
  - needs to be an array of strings that is passed as cmd parameters
- **cmdKeyValue**
  - the key of the dependency and the value are passed in the pattern `--key=value`

{: .warning}
cmdValue expects an array

{: .info}
env, and cmdKeyValue are always strings, If any other type is passed, it will be automatically stringified.
