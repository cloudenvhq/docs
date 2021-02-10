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
$ docker-compose run -e CLOUDENV_BEARER_TOKEN=string-from-dashboard web python console.py
```

