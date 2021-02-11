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

Here's an example of what the full login process looks like:

```console
$ cloudenv login

==> Your current ip address is 2703:8010:3802:fd10:4cbf:4619:7e8b:3fcf

Do you want to firewall this API token to this IP address (enhanced security on servers)? (N/y): y


==> CloudEnv can prevent writes from this computer

Do you want this API token to be read-only? (N/y): n


==> Please visit this url and login or register to authorize this computer: 

https://app.cloudenv.com/cli/afdf2ed31563?verify=378f0d563afe
```

### Setting Up CloudEnv In A New App

The first time you use CloudEnv in an app, you will need to run `cloudenv init` in order to create a record of the app in the CloudEnv servers and initialize the secret encryption key on your machine in the `.cloudenv-secret-key` file. Here's what that process looks like:

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
