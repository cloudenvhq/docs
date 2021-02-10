---
layout: default
title: Bearer Token Authentication
parent: API
nav_order: 1
---

## Bearer Token Authentication

CloudEnv uses Bearer tokens to authenticate API and CLI requests.

You can generate new Bearer tokens at any time at [https://app.cloudenv.com/api_tokens](https://app.cloudenv.com/api_tokens)

![](https://p30.f1.n0.cdn.getcloudapp.com/items/xQunA60B/3fb77845-0762-4970-a2db-94990e3d0f26.jpg?v=2e8ae04f4eb19101c9d5196f61cf1b07)

For tokens that are made for [CI/CD](/pages/tutorials/ci-cd.html), [Docker](/pages/tutorials/docker.html) or other deployment servers, it is strongly recommended to make these tokens READ ONLY so that no modifications will be allowed from these tokens.

Furthermore, you can add IP restrictions for tokens so that certain tokens can only be used with certain IP addresses.
