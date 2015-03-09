# Ø Buildpack

Use Ø is ideal for executing statically compiled binaries or shell script on cloud foundry.

Forked from https://github.com/ryandotsmith/null-buildpack.

## Usage

Create a directory for your app:

```bash
$ mkdir myapp
```

Name the binary or shell script `start`, and ensure it is executable.

```bash
$ cd myapp
$ echo -e "#\!/usr/bin/env bash\n echo hello world" > ./start
$ chmod +x ./start
```

Push the app using the null-buildpack:

```bash
$ cf push my-app --b https://github.com/cloudfoundry-incubator/null-buildpack/archive/master.zip --no-route
$ cf logs my-app
```

## Issues

You will need to make sure that a 64bit linux machine can execute the binary.  With Go on a mac, that means installing and using the cross-compile go tools.
