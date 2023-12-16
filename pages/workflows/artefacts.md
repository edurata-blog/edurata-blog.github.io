---
layout: default
title: Artefacts
parent: Workflows
nav_order: 4
---

## Artefacts

It's possible to automatically upload files (in the following called artefacts) after completion of a step and download on beginning of another.

in order to upload an artefact the interface you need to define the outputs through which you want to upload and inputs through which you download artefacts.

Suppose there is a `step1` that uses `function1` which uploads a file through the output `fileoutput` and a second step `step2` that uses `function2` which downloads the same through the input `fileinput`. The workflow config is the following:

```yaml
steps:
  step1:
    source:
      name: function1
      revision: 1
  step2:
    source:
      name: function2
      revision: 1
    dependencies:
      fileinput: ${step1.fileoutput}
```

The interfaces of the two functions need to be defined in the following way for it to work. Notice the `type: file` on each of the interface items:

_function definition for step1_

```yaml
interface:
  outputs:
    fileoutput:
      type: file
      description: the files that should be returned
```

and

_function definition for step2_

```yaml
interface:
  inputs:
    fileinput:
      type: file
      description: the files that should be put in
```

Now in `function1` you can create the file and then output the filepath to this file in the `fileoutput` attribute for example like this:

```typescript
const fs = require('fs');
const path = require('path');

export async handler(inputs: {
    // This is a path
    inputFile: string
}): {
    // This should be a path as well
    fileoutput: string
} {
    const filePath = "./path/to/local/file.txt"
    const fileAsString = fs.createFileSync(filePath,{ encoding: 'utf8' });

    return {
        fileoutput: filePath
    }
}

```

## Working with typing

nodejs can be typed using typescript and python3 also has an in-built typing system.
