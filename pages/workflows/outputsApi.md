---
layout: default
title: Outputs Api
parent: Workflows
nav_order: 2
---

# Outputs / Callback

For docker runtime, as there is no integration to pass json or artefacts in or out of the container, the api endpoint needs to be called in order to pass json output back to the orchestrator.

The api call is a simple post request to the api endpoint that can be extracted from default environment variables. For example here with python

```python
import os
import json
import requests

return_object = {"output": "some output"}
url = os.environ.get('CALLBACK_URL')
token = os.environ.get('EXECUTION_TOKEN')
headers = {'Authorization': 'Bearer ' + token, 'Content-Type': 'application/json'}
response = requests.post(url, headers=headers, data=json.dumps(return_object))
```

and nodejs

```javascript
import axios from "axios";

const returnObject = { output: "some output" };
const url = process.env.CALLBACK_URL;
const token = process.env.EXECUTION_TOKEN;
const headers = {
  Authorization: "Bearer " + token,
  "Content-Type": "application/json",
};
const response = await axios.post(url, returnObject, { headers });
```
