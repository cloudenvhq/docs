---
layout: default
title: Configuring CloudEnv For Console
parent: Tutorials
---

## Using CloudEnv to Manage Your Console Secrets

You can use CloudEnv to store and manage your local environmental variables, not just your application variables. All you have to do is run `cloudenv init` inside your home directory and add `cloudenv show` to the source step in your shell profile.

```console
$ cd ~
$ cloudenv init
```

## CloudEnv Shell

You can add this to your `.bash_profile` or `.zshrc` file:

```console
envvars=`mktemp`
cloudenv show > $envvars
source $envvars
rm $envvars
```

