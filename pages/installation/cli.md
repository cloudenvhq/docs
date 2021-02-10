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

```
$ cd /var/apps/sampleapp
$ cloudenv init                         # this creates a secret 256-bit key for the project
$ cloudenv push default .env            # this encrypts your existing env vars into CloudEnv
$ cloudenv push development .env.dev    # this encrypts your development-specific env vars into CloudEnv
$ cloudenv push staging .env.staging    # this encrypts your staging-specific env vars into CloudEnv
$ cloudenv push production .env.prod    # this encrypts your production-specific env vars into CloudEnv
$ cloudenv edit production              # edit your env vars locally, as soon as you save,
$                                       #   they are encrypted and uploaded to CloudEnv
$                                       #   and instantly distributed to other team members and environments
```
