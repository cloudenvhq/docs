---
layout: default
title: CloudEnv Python
parent: Installation
---

## CloudEnv Python

```console
$ pip install cloudenv
```

```python
import os
import cloudenv
cloudenv.load_cloudenv()

os.getenv("AWS_SECRET_ACCESS_KEY")
```
