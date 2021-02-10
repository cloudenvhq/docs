---
layout: default
title: curl Examples
parent: API
nav_order: 3
---

## curl Examples

The heart of CloudEnv is a simple object storage API that can be easily manipulated using basic curl commands.

### Get Encrypted Default Secrets

You can validate for yourself that CloudEnv does not keep unencrypted data by trying to access your secrets directly.

```console
$ app='your-app-slug'
$ env='default'
$ bearer=`cat ~/.cloudenvrc`
$ curl -s -H "Authorization: Bearer $bearer" "https://app.cloudenv.com/api/v1/envs?name=$app&environment=$env"

U2FsdGVkX1/FkUaaKi2HX7D3rW5i2EtWVQ+sMMukLU5bViFKKIgxN5a3T/OXgKjH
yG36nJjiHRfk806BmJApRlOdTbCz2RBOUEyV45BX/+wfgOF550KVTwRIBQ+/cwdq
0S3W5Q26z4xDcWFltcIz+iRGzKUgD7M6tJMCGSUzQZFEGtBdPhpHtMVIp5y7nS1k
cSshS1JXMQOJRynnGKAFE6T4erjyW31z4YEBHSGYeiqy7KwXL/6XjuKnpEUY7LNw
q2vfr70/izhNTw7SbgV4PxOIwluDgJSHJ9ScWnPCOxOnSE1IO5k8RSMqHh7hmjMS
5gOyYfuJAbD4Am+U3df51iXGUBzOyRF64OkwldDDDLnF/+CrrAH9GIfpttmm2HwC
...
```

### Get Basic Account Information

You can also use the API to grab the data about the owner of the Bearer token.

```console
$ bearer=`cat ~/.cloudenvrc`
$ curl -s -H "Authorization: Bearer $bearer" "https://app.cloudenv.com/api/v1/me.json"
```

