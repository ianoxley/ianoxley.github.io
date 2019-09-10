---
layout: post
title: "Up and Running with LocalStack and Docker Compose"
date: 2019-09-10
tags:
  -docker
  -aws
  -localstack
---

[LocalStack](https://github.com/localstack/localstack) is a "fully functional local AWS cloud stack" which lets you write
and test AWS code locally.

It's relatively easy to add it to an existing `docker-compose.yml` file. You
add `localstack` as a `service`, and tell it to use one of the localstack
images:

```
services:
  localstack:
    container_name: localstack
    image: localstack/localstack 
```

You can specify which services you need using the `SERVICES` environment
variable e.g. if you're only using SNS and SQS you might do something like
this:

```
services:
  localstack:
    container_name: localstack
    image: localstack/localstack 
    environment:
      - SERVICES=sns:4575,sqs:4576
```

This runs sns on port 4575, and sqs on port 4576. You can expose those ports in
the usual way, and set an `HOSTNAME_EXTERNAL` environment variable if you need
to:

```
services:
  localstack:
    container_name: localstack
    image: localstack/localstack 
    environment:
      - HOSTNAME_EXTERNAL=localstack
      - SERVICES=sns:4575,sqs:4576
    ports:
      - "4575:4575"
      - "4576:4576"
```

The LocalStack container comes with [awslocal](https://github.com/localstack/awscli-local) installed by default, which is
handy to use in a healthcheck to make sure your queues, etc. are available
before your application code tries to use them:

```
services:
  localstack:
    container_name: localstack
    image: localstack/localstack 
    healthcheck:
      test: awslocal sns list-topics && awslocal sqs list-queues
      interval: 3s
      timeout: 10s
    environment:
      - HOSTNAME_EXTERNAL=localstack
      - SERVICES=sns:4575,sqs:4576
    ports:
      - "4575:4575"
      - "4576:4576"
```

Note that when using `awslocal` it will default to the `us-east-1` region
unless you set the `AWS_DEFAULT_REGION` environment
variable to your region of choice:

```
services:
  localstack:
    container_name: localstack
    image: localstack/localstack 
    healthcheck:
      test: awslocal sns list-topics && awslocal sqs list-queues
      interval: 3s
      timeout: 10s
    environment:
      - AWS_DEFAULT_REGION=eu-west-1
      - HOSTNAME_EXTERNAL=localstack
      - SERVICES=sns:4575,sqs:4576
    ports:
      - "4575:4575"
      - "4576:4576"
```

Comprehensive details of what LocalStack provides, and on how you can configure it, are
available on the LocalStack GitHub repo: [https://github.com/localstack/localstack](https://github.com/localstack/localstack)

Hopefully the above is enough to get you up and running.
