---
layout: default
title: Configuring CloudEnv For CI/CD
parent: Tutorials
---

## Configuring CloudEnv For CI/CD

CloudEnv usually uses a file stored in `~/.cloudenvrc` to get access to the [API token](/pages/api/bearer-token.html). That file is created when you run the `cloudenv login` command using the [CloudEnv CLI](/pages/installation/cli.html).

But when deploying through CI/CD, it might be run on a server which does not have that file and did not run `cloudenv login`.

When that is the case, you can use the `CLOUDENV_BEARER_TOKEN` environmental variable to store the [API token](/pages/api/bearer-token.html) instead.

### Example Configuration for Jenkins

The following Jenkins Pipeline code shows an example of how to create a Pipeline using the CloudEnv API environment variables for secrets credentials

```
pipeline {
    agent {
        // Define agent details here
    }
    environment {
        CLOUDENV_BEARER_TOKEN = '... Token generated from https://app.cloudenv.com/api_tokens ...'
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

