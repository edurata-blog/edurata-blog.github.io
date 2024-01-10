---
layout: default
title: Artefacts
parent: Input Output Processing
grand_parent: Workflows
nav_order: 1
---

## Artefacts

It's possible to automatically upload files (in the following called artefacts) after completion of a step and download on beginning of another.

in order to upload an artefact the interface you need to define the outputs through which you want to upload and inputs through which you download artefacts.

### Example

Suppose there is a function `function1` used in two steps. a `step1` that which uploads a file through the output `fileoutput` and a second step `step2` that downloads the same through the input `fileinput`. The workflow config is the following:

```yaml
steps:
  step1:
    source:
      name: function1
      revision: 1
  step2:
    source:
      name: function1
      revision: 1
    dependencies:
      fileinput: ${step1.fileoutput}
```

The interfaces of the function need to be defined in the following way for it to work. Notice the `type: file` on each of the interface items:

_function definition for step1_

```yaml
interface:
  inputs:
    fileinput:
      type: file
      description: the files that should be put in
  outputs:
    fileoutput:
      type: file
      description: the files that should be returned
```

Now in `function1` you can create the file and then output the filepath to this file in the `fileoutput` attribute for example like this:

```typescript
const fs = require('fs');
const path = require('path');

export async handler(inputs: {
    // This is a path
    fileinput: string
}): {
    // This should be a path as well
    fileoutput: string
} {
    const filePath = inputs.fileinput;

    // read existing file if it exists
    if (filePath) {
        const fileAsString = fs.readFileSync(filePath, { encoding: 'utf8' });
    // create new file if it doesn't exist
    } else {
        const fileAsString = fs.createFileSync(filePath,{ encoding: 'utf8' });
    }

    return {
        fileoutput: filePath
    }
}
```

This will result in the file being uploaded to the S3-Bucket and the filepath being passed to the next step. in step2 it is then automatically downloaded and the filepath is passed to the function as the input `fileinput`.
