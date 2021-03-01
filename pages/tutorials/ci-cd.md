---
layout: default
title: Configuring CloudEnv For CI/CD
parent: Tutorials
---

## Configuring CloudEnv For CI/CD

CloudEnv usually uses a file stored in `~/.cloudenvrc` to get access to the [API token](/pages/api/bearer-token.html). That file is created when you run the `cloudenv login` command using the [CloudEnv CLI](/pages/installation/cli.html).

But when deploying through CI/CD, it may not have access to files that are not checked into the source code repository.

In that case, you can use environmental variables to store the [API token](/pages/api/bearer-token.html) and security key instead.

### Example Configuration for Jenkins

The following Jenkins Pipeline code shows an example of how to create a Pipeline using the CloudEnv API environment variables for secrets credentials

```
pipeline {
    agent {
        // Define agent details here
    }
    environment {
        CLOUDENV_BEARER_TOKEN = '... Token generated from https://app.cloudenv.com/api_tokens ...',
        CLOUDENV_APP_SLUG = '... app name slug ...',
        CLOUDENV_APP_SECRET_KEY = '... app secret encryption key ...',
    }
    stages {
        stage('Example stage 1') {
            steps {
                // 
            }
        }
        stage('Example stage 2') {
            steps {
                // 
            }
        }
    }
}
```

### Important Note

It is critical that the `.cloudenv-secret-key` file in the home directory of your application (which you get by running `cloudenv init` or from someone else on your team who has already run `cloudenv init`) is still in the home directory of your application inside your CI/CD pipeline. That secret key can not be put into an environmental variable and should also never be checked into any source code repository.

That file contains your encryption key and without it, your application can not decrypt the data received from CloudEnv's servers.
