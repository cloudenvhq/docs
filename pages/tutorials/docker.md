---
layout: default
title: Configuring CloudEnv For Docker
parent: Tutorials
---

## CloudEnv for Docker

CloudEnv usually uses a file stored in `~/.cloudenvrc` to get access to the [API token](/pages/api/bearer-token.html). That file is created when you run the `cloudenv login` command using the [CloudEnv CLI](/pages/installation/cli.html).

But when deploying through Docker, the container may not have that file.

When that is the case, you can use the `CLOUDENV_BEARER_TOKEN` environmental variable to store the [API token](/pages/api/bearer-token.html) instead.

### Example Configuration for Docker

There are many ways to [configure environmental variables in Docker](https://docs.docker.com/compose/environment-variables/) so if you do not like this way, you can pick any other, but the idea will be the same no matter which implementation you use.

First, [generated a new API token](https://app.cloudenv.com/api_tokens) in the CloudEnv dashboard for use in Docker.

```console
$ docker-compose run -e CLOUDENV_BEARER_TOKEN=string-from-dashboard CLOUDENV_APP_SLUG=app-name CLOUDENV_APP_SECRET_KEY=encryption-key web python console.py
```
### Important Note

It is critical that the `.cloudenv-secret-key` file in the home directory of your application (which you get by running `cloudenv init` or from someone else on your team who has already run `cloudenv init`) is still in the home directory of your application inside your Docker container. That secret key can not be put into an environmental variable and should also never be checked into any source code repository.

That file contains your encryption key and without it, your application can not decrypt the data received from CloudEnv's servers.
