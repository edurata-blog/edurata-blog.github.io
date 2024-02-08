---
layout: default
title: Runtimes
parent: Functions
nav_order: 2
---

# Runtimes

Three runtimes are at the moment supported: Python (v3.10), Nodejs (v20) and Docker.

For both nodejs and python only the basic runtime environment is provided. This means that the functions are running in a container with the runtime environment and the function code. The function code is then executed in the runtime environment.

If you need additional packages or libraries, you can add them using the package management files described in the [dependencies section](dependencies.md).
