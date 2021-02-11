---
layout: default
title: CloudEnv Ruby
parent: Installation
---

## CloudEnv Ruby

Installing CloudEnv's Ruby Library is easy.

```console
$ gem install cloudenv-hq
```

Alternatively, you can add `gem "cloudenv-hq"` if you are using bundler.

Here is an example of a simple `hello.rb` file you could use to test CloudEnv with.

```ruby
gem "cloudenv-hq"
require "cloudenv-hq"

puts ENV.fetch("FOO")
```

But if you run this now you would get an error:

```console
$ ruby hello.rb
Traceback (most recent call last):
	1: from hello.rb:4:in `<main>'
hello.rb:4:in `fetch': key not found: "FOO" (KeyError)
```

That's because we haven't created the CloudEnv environment variable yet.

So the next step is initializing the app:

```console
$ cloudenv init

Name of App: rubytest

==> SUCCESS: You have created the app 'rubytest' in CloudEnv. Try the following command next:

EDITOR=nano cloudenv edit

==> REMEMBER: You need to distribute the following file to all your team members and deployment servers

/home/lucas/rubytest/.cloudenv-secret-key
```

And now you can modify your environmental variables using `cloudenv edit`

```console
$ cloudenv edit

FOO=bar
```

Finally, we can get the output we expect.

```console
$ ruby hello.rb
bar
```
