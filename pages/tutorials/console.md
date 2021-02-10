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

## Bash CloudEnv

```console
echo 'env_file=`mktemp`' >> ~/.bash_profile
echo 'cloudenv show > $env_file' >> ~/bash_profile
echo 'source $env_file' >> ~/bash_profile
echo 'rm $env_file' >> ~/bash_profile
```

## Zsh CloudEnv

```console
echo 'env_file=`mktemp`' >> ~/.zshrc
echo 'cloudenv show > $env_file' >> ~/.zshrc
echo 'source $env_file' >> ~/.zshrc
echo 'rm $env_file' >> ~/.zshrc
```