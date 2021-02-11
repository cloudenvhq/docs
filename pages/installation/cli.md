---
layout: default
title: CloudEnv CLI
parent: Installation
nav_order: 1
---

## CloudEnv CLI

Welcome, here's how easy it is to get started with CloudEnv...

```console
$ bash -c "$(curl -fsSL https://raw.githubusercontent.com/cloudenvhq/install/main/install.sh)"
```

### Logging In

```console
$ cloudenv login
```

### Setting Up CloudEnv In A New App

```console
$ cd /var/apps/sampleapp
$ cloudenv init
Name of App: nodetest

==> SUCCESS: You have created the app 'nodetest' in CloudEnv. Try the following command next:

EDITOR=nano cloudenv edit

==> REMEMBER: You need to distribute the following file to all your team members and deployment servers

/home/lucas/nodetest/.cloudenv-secret-key
```

In case you were curious what's in the `.cloudenv-secret-key` file, it looks something like this:

```console
$ cat .cloudenv-secret-key
slug: nodetest
secret-key: GXWaeMkjqChq5Tt2MNVYJnkdwoFNakXd2JaXDL7nYNHJ4UvXdJx36RHmzY2ueGarNUkn95DaRkBKKcyNhX9pvcqY8NfwTu8Lfc97Rcc3DYbZaX5iRyqVVY2jZyrYPpKhiMf8bFTAxmHkVT7WvJ2owBb7JyAEHG3oYdFEusW8oPFuKcHb4uvrijo9DQehmQrUJ3fDPCx3zfAu2WALk3M9uiGj6JLVpce7aiCEfVghZhdKZyUycqyccNxbzx6a8SoM
```

### Editing Your Environmental Variables

```console
$ cloudenv push default .env            # this encrypts your existing env vars into CloudEnv
$ cloudenv push development .env.dev    # this encrypts your development-specific env vars into CloudEnv
$ cloudenv push staging .env.staging    # this encrypts your staging-specific env vars into CloudEnv
$ cloudenv push production .env.prod    # this encrypts your production-specific env vars into CloudEnv
$ cloudenv edit production              # edit your env vars locally, as soon as you save,
$                                       #   they are encrypted and uploaded to CloudEnv
$                                       #   and instantly distributed to other team members and environments
```
