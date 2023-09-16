---
layout: default
title: artefacts
parent: Deployments
nav_order: 4
---

## Handling of Files (Artefacts)

If you want to make upload files

```typescript
const fs = require('fs');
const path = require('path');

export async handler(inputs: {
    // This is a path
    inputFile: string
}): {
    // This should be a path as well
    outputFile: string
} {
    const fileAsString = fs.readFileSync(inputFile,{ encoding: 'utf8' });

    return
}

```
