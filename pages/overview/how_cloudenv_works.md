---
layout: default
title: How CloudEnv Works
parent: Overview
---

## How CloudEnv Works

CloudEnv is essentially a special-purpose object storage system, similar to AWS S3 or Google Cloud Storage.

What makes it different is that the data stored within CloudEnv is always fully encrypted and that CloudEnv never sees or even generates the encryption keys.

Encryption keys are always and only generated on your machine and are 256 character long random strings.

Those keys are used along with openssl's AES-256-CBC symmetric encryption cipher to keep your data fully encrypted.

Because the encryption keys are on your machine and never leave, it creates an End-to-End encrypted closed loop which is [easy to verify](/pages/api/curl.html) by running some simple `curl` commands on your terminal.

```console
$ curl -s -H "Authorization: Bearer your-bearer-token" "https://app.cloudenv.com/api/v1/envs?name=your-app-name&environment=default"

U2FsdGVkX1/FkUaaKi2HX7D3rW5i2EtWVQ+sMMukLU5bViFKKIgxN5a3T/OXgKjH
yG36nJjiHRfk806BmJApRlOdTbCz2RBOUEyV45BX/+wfgOF550KVTwRIBQ+/cwdq
0S3W5Q26z4xDcWFltcIz+iRGzKUgD7M6tJMCGSUzQZFEGtBdPhpHtMVIp5y7nS1k
cSshS1JXMQOJRynnGKAFE6T4erjyW31z4YEBHSGYeiqy7KwXL/6XjuKnpEUY7LNw
q2vfr70/izhNTw7SbgV4PxOIwluDgJSHJ9ScWnPCOxOnSE1IO5k8RSMqHh7hmjMS
5gOyYfuJAbD4Am+U3df51iXGUBzOyRF64OkwldDDDLnF/+CrrAH9GIfpttmm2HwC
...
```

### CloudEnv Libraries

We have built various client libraries that seamlessly grab the encrypted data, decrypt it with openssl, and load those variables into your typical environment variable access.
