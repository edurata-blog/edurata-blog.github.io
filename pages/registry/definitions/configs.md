---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [@edurata/types](#eduratatypes)
  - [Table of contents](#table-of-contents)
    - [Interfaces](#interfaces)
    - [Type Aliases](#type-aliases)
  - [Type Aliases](#type-aliases-1)
    - [StepDependencyString](#stepdependencystring)
- [Interfaces](#interfaces-1)
  - [Interface: ComputeResources](#interface-computeresources)
    - [Table of contents](#table-of-contents-1)
    - [Properties](#properties)
  - [Interface: Condition](#interface-condition)
    - [Table of contents](#table-of-contents-2)
    - [Properties](#properties-1)
  - [Interface: Config](#interface-config)
    - [Hierarchy](#hierarchy)
    - [Table of contents](#table-of-contents-3)
    - [Properties](#properties-2)
  - [Interface: FunctionConfig](#interface-functionconfig)
    - [Hierarchy](#hierarchy-1)
    - [Table of contents](#table-of-contents-4)
    - [Properties](#properties-3)
  - [Interface: Interface](#interface-interface)
    - [Table of contents](#table-of-contents-5)
    - [Properties](#properties-4)
  - [Interface: InterfaceProperty](#interface-interfaceproperty)
    - [Table of contents](#table-of-contents-6)
    - [Properties](#properties-5)
  - [Interface: SourceImageRepo](#interface-sourceimagerepo)
    - [Table of contents](#table-of-contents-7)
    - [Properties](#properties-6)
  - [Interface: SourceRegistry](#interface-sourceregistry)
    - [Table of contents](#table-of-contents-8)
    - [Properties](#properties-7)
  - [Interface: SourceRepo](#interface-sourcerepo)
    - [Table of contents](#table-of-contents-9)
    - [Properties](#properties-8)
  - [Interface: Step](#interface-step)
    - [Table of contents](#table-of-contents-10)
    - [Properties](#properties-9)
  - [Interface: StepDependency](#interface-stepdependency)
    - [Hierarchy](#hierarchy-2)
    - [Table of contents](#table-of-contents-11)
    - [Properties](#properties-10)
  - [Interface: StepDependencyUseAs](#interface-stepdependencyuseas)
    - [Hierarchy](#hierarchy-3)
    - [Table of contents](#table-of-contents-12)
    - [Properties](#properties-11)
  - [Interface: WorkflowConfig](#interface-workflowconfig)
    - [Hierarchy](#hierarchy-4)
    - [Table of contents](#table-of-contents-13)
    - [Properties](#properties-12)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<a name="readmemd"></a>

@edurata/types

# @edurata/types

## Table of contents

### Interfaces

- [ComputeResources](#interfacescomputeresourcesmd)
- [Condition](#interfacesconditionmd)
- [Config](#interfacesconfigmd)
- [FunctionConfig](#interfacesfunctionconfigmd)
- [Interface](#interfacesinterfacemd)
- [InterfaceProperty](#interfacesinterfacepropertymd)
- [SourceImageRepo](#interfacessourceimagerepomd)
- [SourceRegistry](#interfacessourceregistrymd)
- [SourceRepo](#interfacessourcerepomd)
- [Step](#interfacesstepmd)
- [StepDependency](#interfacesstepdependencymd)
- [StepDependencyUseAs](#interfacesstepdependencyuseasmd)
- [WorkflowConfig](#interfacesworkflowconfigmd)

### Type Aliases

- [StepDependencyString](#stepdependencystring)

## Type Aliases

### StepDependencyString

Ƭ **StepDependencyString**: \`$\{string}.$\{string \| ""}.$\{string \| ""}\`

Schema for a string representing an educational function step dependency.

**`Example`**

```ts
"stepId.outputId.outputPath";
```

# Interfaces

<a name="interfacescomputeresourcesmd"></a>

[@edurata/types](#readmemd) / ComputeResources

## Interface: ComputeResources

### Table of contents

#### Properties

- [cpu](#cpu)
- [memory](#memory)

### Properties

#### cpu

• **cpu**: `number`

The number of vCPUs to allocate for the function. The available CPU values depend on the amount of memory allocated to the function and vice versa.
0.25 vCPU - Available memory values: 0.5 GB, 1 GB, 2 GB

0.5 vCPU - Available memory values: 1 GB, 2 GB, 3 GB, 4 GB

1 vCPU - Available memory values: 2 GB, 3 GB, 4 GB, 5 GB, 6 GB, 7 GB, 8 GB

2 vCPU - Available memory values: 4 GB, 16 GB in increments of 1 GB

4 vCPU - Available memory values: 8 GB, 30 GB in increments of 1 GB

8 vCPU - Available memory values: 16 GB, 60 GB in 4 GB increments
This option requires Linux platform 1.4.0 or later.
16 vCPU - Available memory values: 32 GB, 120 GB in 8 GB increments
This option requires Linux platform 1.4.0 or later.

**`Example`**

```ts
"2";
```

---

#### memory

• **memory**: `number`

The memory allocated. The available memory values depend on the amount of vCPUs allocated to the function and vice versa. See above

**`Example`**

```ts
"16";
```

<a name="interfacesconditionmd"></a>

[@edurata/types](#readmemd) / Condition

## Interface: Condition

Conditions are used to determine if a step should be executed or not.

### Table of contents

#### Properties

- [comparator](#comparator)
- [value](#value)
- [variable](#variable)

### Properties

#### comparator

• **comparator**: `"=="` \| `"!="` \| `">="` \| `">"` \| `"<"` \| `"<="`

The comparator to use. Can be any of the boolean types.

**`Example`**

```ts
"==";
```

---

#### value

• **value**: `string` \| `number` \| `boolean` \| [`StepDependency`](#interfacesstepdependencymd)

The right hand side of the comparison. Can be a step dependency or a primitive value.

---

#### variable

• **variable**: `string` \| `number` \| `boolean` \| [`StepDependency`](#interfacesstepdependencymd)

The left hand side of the comparison. Can be a step dependency or a primitive value.

<a name="interfacesconfigmd"></a>

[@edurata/types](#readmemd) / Config

## Interface: Config

### Hierarchy

- **`Config`**

  ↳ [`WorkflowConfig`](#interfacesworkflowconfigmd)

  ↳ [`FunctionConfig`](#interfacesfunctionconfigmd)

### Table of contents

#### Properties

- [apiRevision](#apirevision)
- [description](#description)
- [interface](#interface)
- [name](#name)
- [resources](#resources)
- [title](#title)

### Properties

#### apiRevision

• **apiRevision**: `"edurata.io/v1"`

Refers to the version of this schema and should be updated whenever the schema changes

---

#### description

• `Optional` **description**: `string`

An additional description of the workflow or function

---

#### interface

• `Optional` **interface**: [`Interface`](#interfacesinterfacemd)

The schema of inputs and outputs of this workflow or function

---

#### name

• **name**: `string`

An identifier that is unique in the registry. It is used as reference in deployments or workflows.

---

#### resources

• `Optional` **resources**: [`ComputeResources`](#interfacescomputeresourcesmd)

The compute resources to assign. The resources specified of function level will be overriden on workflow level.

---

#### title

• `Optional` **title**: `string`

A short title that describes the workflow or function. This is NOT the id that will be used in the registry!

<a name="interfacesfunctionconfigmd"></a>

[@edurata/types](#readmemd) / FunctionConfig

## Interface: FunctionConfig

Represents the configuration schema for a function.

### Hierarchy

- [`Config`](#interfacesconfigmd)

  ↳ **`FunctionConfig`**

### Table of contents

#### Properties

- [apiRevision](#apirevision)
- [description](#description)
- [entrypoint](#entrypoint)
- [exclude](#exclude)
- [include](#include)
- [interface](#interface)
- [name](#name)
- [resources](#resources)
- [runtime](#runtime)
- [title](#title)

### Properties

#### apiRevision

• **apiRevision**: `"edurata.io/v1"`

Refers to the version of this schema and should be updated whenever the schema changes

##### Inherited from

[Config](#interfacesconfigmd).[apiRevision](#apirevision)

---

#### description

• `Optional` **description**: `string`

An additional description of the workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[description](#description)

---

#### entrypoint

• `Optional` **entrypoint**: `string`

Points to the entrypoint of the function. Defaults to index.js, index.py, index.sh, etc.

---

#### exclude

• `Optional` **exclude**: `string`[]

Specifies which files to exclude from the function. Can be a glob pattern. Defaults to none.

---

#### include

• `Optional` **include**: `string`[]

Specifies which files to include in the function. Can be a glob pattern. Defaults to all files in the same directory as the entrypoint.

---

#### interface

• `Optional` **interface**: [`Interface`](#interfacesinterfacemd)

The schema of inputs and outputs of this workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[interface](#interface)

---

#### name

• **name**: `string`

An identifier that is unique in the registry. It is used as reference in deployments or workflows.

##### Inherited from

[Config](#interfacesconfigmd).[name](#name)

---

#### resources

• `Optional` **resources**: [`ComputeResources`](#interfacescomputeresourcesmd)

The compute resources to assign. The resources specified of function level will be overriden on workflow level.

##### Inherited from

[Config](#interfacesconfigmd).[resources](#resources)

---

#### runtime

• `Optional` **runtime**: `"nodejs16"` \| `"nodejs18"` \| `"nodejs20"` \| `"python3_7"` \| `"python3_8"` \| `"bash"`

Specifies the programming language the code is written in.

---

#### title

• `Optional` **title**: `string`

A short title that describes the workflow or function. This is NOT the id that will be used in the registry!

##### Inherited from

[Config](#interfacesconfigmd).[title](#title)

<a name="interfacesinterfacemd"></a>

[@edurata/types](#readmemd) / Interface

## Interface: Interface

Schema for an interface of a workflow or function.

**`Example`**

```typescript
{
 inputs: {
   required: ["name"],
   properties: {
     name: {
       type: "string",
       title: "Name",
       description: "The name of the person",
     }
  }
}
```

### Table of contents

#### Properties

- [inputs](#inputs)
- [outputs](#outputs)

### Properties

#### inputs

• `Optional` **inputs**: `Object`

##### Type declaration

| Name          | Type                                                                         |
| :------------ | :--------------------------------------------------------------------------- |
| `properties?` | \{ `[key: string]`: [`InterfaceProperty`](#interfacesinterfacepropertymd); } |
| `required?`   | `string`[]                                                                   |

---

#### outputs

• `Optional` **outputs**: `Object`

##### Type declaration

| Name          | Type                                                                         |
| :------------ | :--------------------------------------------------------------------------- |
| `properties?` | \{ `[key: string]`: [`InterfaceProperty`](#interfacesinterfacepropertymd); } |
| `required?`   | `string`[]                                                                   |

<a name="interfacesinterfacepropertymd"></a>

[@edurata/types](#readmemd) / InterfaceProperty

## Interface: InterfaceProperty

Inspired by JSON Schema for easier conversion from and to other tools.

**`See`**

https://tools.ietf.org/html/draft-handrews-json-schema-validation-01

### Table of contents

#### Properties

- [const](#const)
- [default](#default)
- [description](#description)
- [enum](#enum)
- [examples](#examples)
- [items](#items)
- [properties](#properties)
- [required](#required)
- [title](#title)
- [type](#type)

### Properties

#### const

• `Optional` **const**: [`InterfaceProperty`](#interfacesinterfacepropertymd)

---

#### default

• `Optional` **default**: [`InterfaceProperty`](#interfacesinterfacepropertymd)

---

#### description

• `Optional` **description**: `string`

---

#### enum

• `Optional` **enum**: (`string` \| `number` \| `boolean`)[]

---

#### examples

• `Optional` **examples**: [`InterfaceProperty`](#interfacesinterfacepropertymd)[]

---

#### items

• `Optional` **items**: [`InterfaceProperty`](#interfacesinterfacepropertymd)

---

#### properties

• `Optional` **properties**: `Object`

##### Index signature

▪ [key: `string`]: [`InterfaceProperty`](#interfacesinterfacepropertymd)

---

#### required

• `Optional` **required**: `string`[]

---

#### title

• `Optional` **title**: `string`

---

#### type

• **type**: [`Interface`](#interfacesinterfacemd)

<a name="interfacessourceimagerepomd"></a>

[@edurata/types](#readmemd) / SourceImageRepo

## Interface: SourceImageRepo

If the source is an image, you can point to an image repo and its tag.

### Table of contents

#### Properties

- [imageRepoUrl](#imagerepourl)
- [tag](#tag)

### Properties

#### imageRepoUrl

• **imageRepoUrl**: `string`

The url of the image repository. If dockerhub is used, url is optional.

**`Example`**

```ts
"docker.io/edurata";
```

**`Example`**

```ts
"ghcr.io/edurata";
```

**`Example`**

```ts
"quay.io/edurata";
```

---

#### tag

• **tag**: `string`

The tag of the image.

**`Example`**

```ts
"latest";
```

**`Example`**

```ts
"12";
```

**`Example`**

```ts
"1.0.0";
```

<a name="interfacessourceregistrymd"></a>

[@edurata/types](#readmemd) / SourceRegistry

## Interface: SourceRegistry

If the source is already in the registry you can point to an entry of the registry.

### Table of contents

#### Properties

- [name](#name)
- [revision](#revision)

### Properties

#### name

• **name**: `string`

The name of the function in the registry.

**`Example`**

```ts
"my-function";
```

---

#### revision

• `Optional` **revision**: `string`

The revision of the function in the registry.

**`Example`**

```ts
"12";
```

<a name="interfacessourcerepomd"></a>

[@edurata/types](#readmemd) / SourceRepo

## Interface: SourceRepo

If the source is a git repository, this is the schema for it.

### Table of contents

#### Properties

- [path](#path)
- [ref](#ref)
- [repoUrl](#repourl)

### Properties

#### path

• `Optional` **path**: `string`

the path of where to find the function code inside the repository

**`Example`**

```ts
"tests/sleep";
```

---

#### ref

• `Optional` **ref**: `string`

The ref of the git repository to use. Defaults to "main".

**`Example`**

```ts
"main";
```

---

#### repoUrl

• **repoUrl**: `string`

the url of the git repository

**`Example`**

```ts
"https://github.com/Edurata/edurata-functions";
```

<a name="interfacesstepmd"></a>

[@edurata/types](#readmemd) / Step

## Interface: Step

Schema for an educational function step.

### Table of contents

#### Properties

- [dependencies](#dependencies)
- [description](#description)
- [foreach](#foreach)
- [if](#if)
- [source](#source)

### Properties

#### dependencies

• `Optional` **dependencies**: `Object`

Specifies where to get the input data (from other steps or the global inputs of the workflow defined in
the "interface" attribute at the top). Each key must be an input of this step and should be defined in
FunctionSchema.interface.inputs of the function defined in "source".

##### Index signature

▪ [key: `string`]: [`StepDependency`](#interfacesstepdependencymd) \| [`StepDependencyString`](#stepdependencystring)

---

#### description

• `Optional` **description**: `string`

An additional description next to the key of the step.

---

#### foreach

• `Optional` **foreach**: [`StepDependency`](#interfacesstepdependencymd) \| \`$\{string}.$\{string}.$\{string}\`

If defined and the dependency is of type array, this step will loop over the array. The dependencies
attribute can then use "each" as StepDependencySchema.stepId, pointing to each iteration.

---

#### if

• `Optional` **if**: [`Condition`](#interfacesconditionmd)

If defined, this step will only execute if the condition is true.

---

#### source

• `Optional` **source**: `Source`

Specifies the source from which to obtain the code to execute in this step.

<a name="interfacesstepdependencymd"></a>

[@edurata/types](#readmemd) / StepDependency

## Interface: StepDependency

Schema for an educational function step dependency.

**`Example`**

assuming the step "inputs" has an output "name" with the value "John"

```typescript
{
 stepId: "inputs",
 outputId: "name",
}
```

**`Example`**

assuming the step "inputs" has an output "name" that is a complex object with a key "firstName" with the value "John"

```typescript
{
 stepId: "inputs",
 outputId: "name",
 outputPath: "firstName",
}
```

### Hierarchy

- **`StepDependency`**

  ↳ [`StepDependencyUseAs`](#interfacesstepdependencyuseasmd)

### Table of contents

#### Properties

- [dependencies](#dependencies)
- [outputId](#outputid)
- [outputPath](#outputpath)
- [stepId](#stepid)
- [useAs](#useas)
- [value](#value)

### Properties

#### dependencies

• `Optional` **dependencies**: [`StepDependency`](#interfacesstepdependencymd)[]

If the dependency is a string with interpolated values, these are the interpolated values, if any.
These are mostly autopopulated and usually don't need to be set manually.

---

#### outputId

• `Optional` **outputId**: `string`

the name of the output of a step (thereby its function). has to be one of the outputs defined in
FunctionSchema.interface.outputs of the dependent step mentioned with "stepId"

---

#### outputPath

• `Optional` **outputPath**: `string`

only used when the output is a complex object and the value is inside. is a string with dot notation
to point to the value. e.g. "data.name" to point to the value of the key "name" inside the object
"data".

**`Example`**

```ts
"data.name";
```

---

#### stepId

• `Optional` **stepId**: `string`

the step which to depend on. Needs to be one defined in the "steps" attribute of the workflow
definition. Can be "inputs" to refer to the global inputs of the workflow. Can be "each" if the
attribute "foreach" in the parent step is defined.

---

#### useAs

• `Optional` **useAs**: `"ENV"` \| `"CMD_VALUE"` \| `"CMD_KEY_VALUE"` \| `"PARAMETER"`

If the current step source of this dependency is a container image, this specifies whether to use the dependency as an environment variable or as a command line argument.

**`Example`**

```ts
"ENV" -> the key of the dependency will be used as the name of the environment variable and the value as the value of the environment variable
```

**`Example`**

```ts
"CMD_VALUE" -> the value of the dependency will be used as the value of the command line argument like so "VALUE"
```

---

#### value

• `Optional` **value**: `string`

If you want to pass in a value directly instead of a step dependency, you can use this attribute.
You can also use interpolation here.

**`Example`**

```ts
"examplestring";
```

**`Example`**

```ts
"${inputs.name} is here!";
```

<a name="interfacesstepdependencyuseasmd"></a>

[@edurata/types](#readmemd) / StepDependencyUseAs

## Interface: StepDependencyUseAs

Schema for an educational function step dependency.

**`Example`**

assuming the step "inputs" has an output "name" with the value "John"

```typescript
{
 stepId: "inputs",
 outputId: "name",
}
```

**`Example`**

assuming the step "inputs" has an output "name" that is a complex object with a key "firstName" with the value "John"

```typescript
{
 stepId: "inputs",
 outputId: "name",
 outputPath: "firstName",
}
```

### Hierarchy

- [`StepDependency`](#interfacesstepdependencymd)

  ↳ **`StepDependencyUseAs`**

### Table of contents

#### Properties

- [dependencies](#dependencies)
- [outputId](#outputid)
- [outputPath](#outputpath)
- [stepId](#stepid)
- [useAs](#useas)
- [value](#value)

### Properties

#### dependencies

• `Optional` **dependencies**: [`StepDependency`](#interfacesstepdependencymd)[]

If the dependency is a string with interpolated values, these are the interpolated values, if any.
These are mostly autopopulated and usually don't need to be set manually.

##### Inherited from

[StepDependency](#interfacesstepdependencymd).[dependencies](#dependencies)

---

#### outputId

• `Optional` **outputId**: `string`

the name of the output of a step (thereby its function). has to be one of the outputs defined in
FunctionSchema.interface.outputs of the dependent step mentioned with "stepId"

##### Inherited from

[StepDependency](#interfacesstepdependencymd).[outputId](#outputid)

---

#### outputPath

• `Optional` **outputPath**: `string`

only used when the output is a complex object and the value is inside. is a string with dot notation
to point to the value. e.g. "data.name" to point to the value of the key "name" inside the object
"data".

**`Example`**

```ts
"data.name";
```

##### Inherited from

[StepDependency](#interfacesstepdependencymd).[outputPath](#outputpath)

---

#### stepId

• `Optional` **stepId**: `string`

the step which to depend on. Needs to be one defined in the "steps" attribute of the workflow
definition. Can be "inputs" to refer to the global inputs of the workflow. Can be "each" if the
attribute "foreach" in the parent step is defined.

##### Inherited from

[StepDependency](#interfacesstepdependencymd).[stepId](#stepid)

---

#### useAs

• `Optional` **useAs**: `"ENV"` \| `"CMD_VALUE"` \| `"CMD_KEY_VALUE"` \| `"PARAMETER"`

If the current step source of this dependency is a container image, this specifies whether to use the dependency as an environment variable or as a command line argument.

**`Example`**

```ts
"ENV" -> the key of the dependency will be used as the name of the environment variable and the value as the value of the environment variable
```

**`Example`**

```ts
"CMD_VALUE" -> the value of the dependency will be used as the value of the command line argument like so "VALUE"
```

##### Inherited from

[StepDependency](#interfacesstepdependencymd).[useAs](#useas)

---

#### value

• `Optional` **value**: `string`

If you want to pass in a value directly instead of a step dependency, you can use this attribute.
You can also use interpolation here.

**`Example`**

```ts
"examplestring";
```

**`Example`**

```ts
"${inputs.name} is here!";
```

##### Inherited from

[StepDependency](#interfacesstepdependencymd).[value](#value)

<a name="interfacesworkflowconfigmd"></a>

[@edurata/types](#readmemd) / WorkflowConfig

## Interface: WorkflowConfig

Represents the configuration schema for a workflow.

### Hierarchy

- [`Config`](#interfacesconfigmd)

  ↳ **`WorkflowConfig`**

### Table of contents

#### Properties

- [apiRevision](#apirevision)
- [description](#description)
- [interface](#interface)
- [name](#name)
- [resources](#resources)
- [schedule](#schedule)
- [steps](#steps)
- [title](#title)

### Properties

#### apiRevision

• **apiRevision**: `"edurata.io/v1"`

Refers to the version of this schema and should be updated whenever the schema changes

##### Inherited from

[Config](#interfacesconfigmd).[apiRevision](#apirevision)

---

#### description

• `Optional` **description**: `string`

An additional description of the workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[description](#description)

---

#### interface

• `Optional` **interface**: [`Interface`](#interfacesinterfacemd)

The schema of inputs and outputs of this workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[interface](#interface)

---

#### name

• **name**: `string`

An identifier that is unique in the registry. It is used as reference in deployments or workflows.

##### Inherited from

[Config](#interfacesconfigmd).[name](#name)

---

#### resources

• `Optional` **resources**: [`ComputeResources`](#interfacescomputeresourcesmd)

The compute resources to assign. The resources specified of function level will be overriden on workflow level.

##### Inherited from

[Config](#interfacesconfigmd).[resources](#resources)

---

#### schedule

• **schedule**: `string`

A cron schedule that determines when the workflow should be executed.

**`Example`**

```ts
"0 0 * * *" -> every day at midnight
```

**`Example`**

```ts
"0 0 * * 0" -> every sunday at midnight
```

**`Example`**

```ts
"0 0 1 * *" -> every first day of the month at midnight
```

**`Example`**

```ts
"0 0 1 1 *" -> every first day of the year at midnight
```

**`Example`**

```ts
"0 0 1 1 0" -> every first sunday of the year at midnight
```

---

#### steps

• **steps**: `Object`

Each step of the workflow specified by a unique key and its definition as a value.
The order of execution and dataflow is inferred by "dependencies".

##### Index signature

▪ [key: `string`]: [`Step`](#interfacesstepmd)

---

#### title

• `Optional` **title**: `string`

A short title that describes the workflow or function. This is NOT the id that will be used in the registry!

##### Inherited from

[Config](#interfacesconfigmd).[title](#title)

<a name="schemamd"></a>
