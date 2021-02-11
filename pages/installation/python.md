---
layout: default
title: CloudEnv Python
parent: Installation
---

## CloudEnv Python

Installing CloudEnv's Python Library is easy.

```console
$ pip install cloudenv
```

Or if you are using Python 3, you might try this command:

```console
$ pip3 install cloudenv
```

Here is an example of a simple `hello.py` file you could use to test CloudEnv with.

```python
import os
import cloudenv
cloudenv.load_cloudenv()

print(os.getenv("FOO"))
```

But if you run this now you would get a strange result:

```console
$ python hello.py
None
```

That's because we haven't created the CloudEnv environment variable yet.

So the next step is initializing the app:

```console
$ cloudenv init
Name of App: pythontest

==> SUCCESS: You have created the app 'pythontest' in CloudEnv. Try the following command next:

EDITOR=nano cloudenv edit

==> REMEMBER: You need to distribute the following file to all your team members and deployment servers

/home/lucas/pythontest/.cloudenv-secret-key
```

And now you can modify your environmental variables using `cloudenv edit`

```console
$ cloudenv edit
FOO=bar
```

Finally, we can get the output we expect.

```console
$ python hello.py
bar
```
