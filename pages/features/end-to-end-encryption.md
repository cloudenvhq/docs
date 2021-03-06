---
layout: default
title: End-to-End Encryption
parent: Features
---

## End-to-End Encryption

Why can we not display your secrets? Because we never at any point have access to your encryption key.

![](https://p30.f1.n0.cdn.getcloudapp.com/items/qGuXvXXv/d7313bae-0879-43ff-ad5e-50ff427e8fb0.jpg?v=a5925db822ef15c3c8ec1ccdff003446)

CloudEnv is essentially a special-purpose object storage system, similar to AWS S3 or Google Cloud Storage.

What makes it different is that the data stored within CloudEnv is always fully encrypted and that CloudEnv never sees or even generates the encryption keys.

Encryption keys are always and only generated on your machine and are 256 character long random strings.

Those keys are used along with `openssl`'s AES-256-CBC symmetric encryption cipher to keep your data fully encrypted.

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

You need to pass this data through a simple `openssl` command in order to unscramble your secrets. 

```console
$ openssl enc -a -aes-256-cbc -md sha512 -d -pass pass:"$secretkey" -in "$encrypted_file"

FOO=BAR
DATABASE_PASSWORD=123
AWS_SECRET_ACCESS_KEY=138ur83uf83f8h
```

The best part is that the `$secretkey` is never in our hands. We can't see your keys, so we can't see your secrets.

You can verify that this is true by looking at the first few lines of our CLI's open-source source code: [https://github.com/cloudenvhq/cli/blob/master/src/initialize.sh](https://github.com/cloudenvhq/cli/blob/master/src/initialize.sh)

Once that code is on your machine, there is no way for us to change it or try to do anything malicious. Your secrets are auditably safe and secure.
