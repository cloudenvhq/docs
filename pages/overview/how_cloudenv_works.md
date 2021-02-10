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

### CloudEnv Libraries

We have built various client libraries that seamlessly grab the encrypted data, decrypt it with openssl, and load those variables into your typical environment variable access.
