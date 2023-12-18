---
layout: default
title: Code Structure
parent: Functions
nav_order: 1
---

# Code Structure

## The handler function

If you have worked with AWS lambda functions before you will know that a handler function is expected in the root directory as an entry point into your function. The convention here is:

- **The handler functions needs to be called handler**.
- **The handler functions needs to be exported**.

## Inputs & Outputs of functions

Both inputs and outputs of a function are complex objects with the keys equal to the inputs and outputs defined in the interface.

```python
def handler(inputs):
    if 'sender' not in inputs or 'to' not in inputs:
        raise Exception('required inputs not present')
    sender = inputs.get("sender")
    to = inputs.get("to")
    subject = inputs.get("subject","")
    body = inputs.get("body", "")
    success = send_email(sender, to, subject, body)

    return {
        success: success
    }

```
