---
layout: default
title: CloudEnv Node
parent: Installation
---

## CloudEnv Node

Installing CloudEnv's Node Library is easy.

```console
$ npm install cloudenv-hq --save
```

Or if you are using Yarn, you might try this command:

```console
$ yarn add cloudenv-hq
```

Here is an example of a simple `hello.js` file you could use to test CloudEnv with.

```javascript
require("cloudenv-hq")

console.log(process.env.FOO)
```

But if you run this now you would get a strange result:

```console
$ node hello.js
undefined
```

That's because we haven't created the CloudEnv environment variable yet.

So the next step is initializing the app:

```console
$ cloudenv init
Name of App: nodetest

==> SUCCESS: You have created the app 'nodetest' in CloudEnv. Try the following command next:

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
$ node hello.js
bar
```
