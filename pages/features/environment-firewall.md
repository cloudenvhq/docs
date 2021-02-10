---
layout: default
title: Environment Firewall
parent: Features
---

## Environment Firewall

Creating allow and deny lists for an app is easy with CloudEnv.

Just open the app's page from the [CloudEnv Dashboard](https://app.leadx.org/) and scroll down to see a section like this.

![](https://p30.f1.n0.cdn.getcloudapp.com/items/YEuXyX2O/5330b7e0-e609-42d7-a6e3-165582d701bd.jpg?source=viewer&v=6a12863b7942af3a0e4708c0fd4e553e)

### Adding an IP Address or Subnet

You can press the purple plus button to add a new Allow or Deny subnet

![](https://p30.f1.n0.cdn.getcloudapp.com/items/nOulnlql/4a1f145b-7b53-4fef-b72f-c754eae2e0b2.jpg?v=eb1217fd0ca50e738ae3ecd347859c9b)

### Notifications for IP Addresses or Subnets

When you are adding a new IP address or subnet, you can check one of two boxes:

  1) Notify Organization Admins When Env Vars Are Accessed from This IP Address
  2) Require Email Authorization from Organization Admins Before Allowing This IP Address
  
The first box will send an email to all of an organizations admin accounts whenever the secrets are accessed from this block. This allows you to keep a close eye on certain IP addresses.

This email will look like this:

![](https://p30.f1.n0.cdn.getcloudapp.com/items/v1uNxb2p/b5fdc6e2-8f0c-44f3-9e05-52253ab528a3.jpg?v=fab7031629919609b6b3d20063505c44)

You can also setup notification for the Deny list and get an email any time any access is denied.

The second box will block the attempt until an admin actually manually approves access.
