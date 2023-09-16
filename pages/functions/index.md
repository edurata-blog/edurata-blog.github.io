---
layout: default
title: Functions
has_children: true
nav_order: 4
---

# Functions

Functions are chunks of code with minimal functionality that can be chained together in order to build a workflow. We enforce a minmal amount of conventions to make the whole ecosystem both scaleable and easy to use for everyone.

## The handler function

If you have worked with AWS lambda functions before you will know that a handler function is expected in the root directory as an entry point into your function. The convention here is:

- **The handler functions needs to be called handler**.
- **The handler functions needs to be exported**: If you don' export the function it is not possible for our wrapper to pick it up.
