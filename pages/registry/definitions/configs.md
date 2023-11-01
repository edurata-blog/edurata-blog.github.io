---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
---
layout: default
title: Schema
parent: Definitions
grand_parent: Registry
---
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
    - [Source](#source)
    - [StepDependencyString](#stepdependencystring)
- [Interfaces](#interfaces-1)
  - [Interface: Condition](#interface-condition)
    - [Table of contents](#table-of-contents-1)
    - [Properties](#properties)
  - [Interface: Config](#interface-config)
    - [Hierarchy](#hierarchy)
    - [Table of contents](#table-of-contents-2)
    - [Properties](#properties-1)
  - [Interface: FunctionConfig](#interface-functionconfig)
    - [Hierarchy](#hierarchy-1)
    - [Table of contents](#table-of-contents-3)
    - [Properties](#properties-2)
  - [Interface: Interface](#interface-interface)
    - [Table of contents](#table-of-contents-4)
    - [Properties](#properties-3)
  - [Interface: InterfaceProperty](#interface-interfaceproperty)
    - [Table of contents](#table-of-contents-5)
    - [Properties](#properties-4)
  - [Interface: SourceImageRepo](#interface-sourceimagerepo)
    - [Table of contents](#table-of-contents-6)
    - [Properties](#properties-5)
  - [Interface: SourceRegistry](#interface-sourceregistry)
    - [Table of contents](#table-of-contents-7)
    - [Properties](#properties-6)
  - [Interface: SourceRepo](#interface-sourcerepo)
    - [Table of contents](#table-of-contents-8)
    - [Properties](#properties-7)
  - [Interface: Step](#interface-step)
    - [Table of contents](#table-of-contents-9)
    - [Properties](#properties-8)
  - [Interface: StepDependency](#interface-stepdependency)
    - [Table of contents](#table-of-contents-10)
    - [Properties](#properties-9)
  - [Interface: WorkflowConfig](#interface-workflowconfig)
    - [Hierarchy](#hierarchy-2)
    - [Table of contents](#table-of-contents-11)
    - [Properties](#properties-10)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


<a name="readmemd"></a>

@edurata/types

# @edurata/types

## Table of contents

### Interfaces

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
- [WorkflowConfig](#interfacesworkflowconfigmd)

### Type Aliases

- [Source](#source)
- [StepDependencyString](#stepdependencystring)

## Type Aliases

### Source

Ƭ **Source**: [`SourceRegistry`](#interfacessourceregistrymd) \| [`SourceRepo`](#interfacessourcerepomd) \| [`SourceImageRepo`](#interfacessourceimagerepomd)

___

### StepDependencyString

Ƭ **StepDependencyString**: \`${string}.${string \| ""}.${string \| ""}\`

Schema for a string representing an educational function step dependency.

**`Example`**

```ts
"stepId.outputId.outputPath"
```

# Interfaces


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

• **comparator**: ``"=="`` \| ``"!="`` \| ``">="`` \| ``">"`` \| ``"<"`` \| ``"<="``

The comparator to use. Can be any of the boolean types.

**`Example`**

```ts
"=="
```

___

#### value

• **value**: `string` \| `number` \| `boolean` \| [`StepDependency`](#interfacesstepdependencymd)

The right hand side of the comparison. Can be a step dependency or a primitive value.

___

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
- [title](#title)

### Properties

#### apiRevision

• **apiRevision**: ``"edurata.io/v1"``

Refers to the version of this schema and should be updated whenever the schema changes

___

#### description

• `Optional` **description**: `string`

An additional description of the workflow or function

___

#### interface

• `Optional` **interface**: [`Interface`](#interfacesinterfacemd)

The schema of inputs and outputs of this workflow or function

___

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
- [runtime](#runtime)
- [title](#title)

### Properties

#### apiRevision

• **apiRevision**: ``"edurata.io/v1"``

Refers to the version of this schema and should be updated whenever the schema changes

##### Inherited from

[Config](#interfacesconfigmd).[apiRevision](#apirevision)

___

#### description

• `Optional` **description**: `string`

An additional description of the workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[description](#description)

___

#### entrypoint

• **entrypoint**: `string`

Points to the entrypoint of the function. Defaults to index.js, index.py, index.sh, etc.

___

#### exclude

• `Optional` **exclude**: `string`[]

Specifies which files to exclude from the function. Can be a glob pattern. Defaults to none.

___

#### include

• `Optional` **include**: `string`[]

Specifies which files to include in the function. Can be a glob pattern. Defaults to all files in the same directory as the entrypoint.

___

#### interface

• `Optional` **interface**: [`Interface`](#interfacesinterfacemd)

The schema of inputs and outputs of this workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[interface](#interface)

___

#### runtime

• **runtime**: `RunnerRuntime`

Specifies the programming language the code is written in.

___

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

| Name | Type |
| :------ | :------ |
| `properties?` | `Record`<`string`, [`InterfaceProperty`](#interfacesinterfacepropertymd)\> |
| `required?` | `string`[] |

___

#### outputs

• `Optional` **outputs**: `Object`

##### Type declaration

| Name | Type |
| :------ | :------ |
| `properties?` | `Record`<`string`, [`InterfaceProperty`](#interfacesinterfacepropertymd)\> |
| `required?` | `string`[] |


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

___

#### default

• `Optional` **default**: [`InterfaceProperty`](#interfacesinterfacepropertymd)

___

#### description

• `Optional` **description**: `string`

___

#### enum

• `Optional` **enum**: (`string` \| `number` \| `boolean`)[]

___

#### examples

• `Optional` **examples**: [`InterfaceProperty`](#interfacesinterfacepropertymd)[]

___

#### items

• `Optional` **items**: [`InterfaceProperty`](#interfacesinterfacepropertymd)

___

#### properties

• `Optional` **properties**: `Record`<`string`, [`InterfaceProperty`](#interfacesinterfacepropertymd)\>

___

#### required

• `Optional` **required**: `string`[]

___

#### title

• `Optional` **title**: `string`

___

#### type

• **type**: `RunnerRuntime`


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
"docker.io/edurata"
```

**`Example`**

```ts
"ghcr.io/edurata"
```

**`Example`**

```ts
"quay.io/edurata"
```

___

#### tag

• **tag**: `string`

The tag of the image.

**`Example`**

```ts
"latest"
```

**`Example`**

```ts
"12"
```

**`Example`**

```ts
"1.0.0"
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
"my-function"
```

___

#### revision

• `Optional` **revision**: `string`

The revision of the function in the registry.

**`Example`**

```ts
"12"
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
"tests/sleep"
```

___

#### ref

• `Optional` **ref**: `string`

The ref of the git repository to use. Defaults to "main".

**`Example`**

```ts
"main"
```

___

#### repoUrl

• **repoUrl**: `string`

the url of the git repository

**`Example`**

```ts
"https://github.com/Edurata/edurata-functions"
```


<a name="interfacesstepmd"></a>

[@edurata/types](#readmemd) / Step

## Interface: Step

Schema for an educational function step.

### Table of contents

#### Properties

- [action](#action)
- [dependencies](#dependencies)
- [foreach](#foreach)
- [if](#if)
- [source](#source)
- [title](#title)

### Properties

#### action

• `Optional` **action**: `string`

An identifier with a logo to provide a quick idea about what the step does, purely for visibility.

___

#### dependencies

• `Optional` **dependencies**: `Record`<`string`, [`StepDependency`](#interfacesstepdependencymd) \| \`${string}.${string}.${string}\`\>

Specifies where to get the input data (from other steps or the global inputs of the workflow defined in
the "interface" attribute at the top). Each key must be an input of this step and should be defined in
FunctionSchema.interface.inputs of the function defined in "source".

___

#### foreach

• `Optional` **foreach**: [`StepDependency`](#interfacesstepdependencymd) \| \`${string}.${string}.${string}\`

If defined and the dependency is of type array, this step will loop over the array. The dependencies
attribute can then use "each" as StepDependencySchema.stepId, pointing to each iteration.

___

#### if

• `Optional` **if**: [`Condition`](#interfacesconditionmd)

If defined, this step will only execute if the condition is true.

___

#### source

• `Optional` **source**: [`Source`](#source)

Specifies the source from which to obtain the code to execute in this step.

___

#### title

• `Optional` **title**: `string`

An additional identifier next to the key of the step.


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

### Table of contents

#### Properties

- [outputId](#outputid)
- [outputPath](#outputpath)
- [stepId](#stepid)

### Properties

#### outputId

• `Optional` **outputId**: `string`

the name of the output of a step (thereby its function). has to be one of the outputs defined in
FunctionSchema.interface.outputs of the dependent step mentioned with "stepId"

___

#### outputPath

• `Optional` **outputPath**: `string`

only used when the output is a complex object and the value is inside. is a string with dot notation
to point to the value. e.g. "data.name" to point to the value of the key "name" inside the object
"data".

**`Example`**

```ts
"data.name"
```

___

#### stepId

• **stepId**: `string`

the step which to depend on. Needs to be one defined in the "steps" attribute of the workflow
definition. Can be "inputs" to refer to the global inputs of the workflow. Can be "each" if the
attribute "foreach" in the parent step is defined.


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
- [steps](#steps)
- [title](#title)

### Properties

#### apiRevision

• **apiRevision**: ``"edurata.io/v1"``

Refers to the version of this schema and should be updated whenever the schema changes

##### Inherited from

[Config](#interfacesconfigmd).[apiRevision](#apirevision)

___

#### description

• `Optional` **description**: `string`

An additional description of the workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[description](#description)

___

#### interface

• `Optional` **interface**: [`Interface`](#interfacesinterfacemd)

The schema of inputs and outputs of this workflow or function

##### Inherited from

[Config](#interfacesconfigmd).[interface](#interface)

___

#### steps

• **steps**: `Record`<`string`, [`Step`](#interfacesstepmd)\>

Each step of the workflow specified by a unique key and its definition as a value.
The order of execution and dataflow is inferred by "dependencies".

___

#### title

• `Optional` **title**: `string`

A short title that describes the workflow or function. This is NOT the id that will be used in the registry!

##### Inherited from

[Config](#interfacesconfigmd).[title](#title)


<a name="schemamd"></a>
