# CloudFoundry RabbitMQ Delayed Message Exchange BOSH Addon Release

This repository contains a BOSH addon release that will add and configure the rabbitmq_delayed_message_exchange plugin.

The following plugin binaries are included in this repository under **final_blobs**:

| RabbitMQ Version | Plugin Version |
|------------------|----------------|
| 3.6.x            | 20171215-3.6.x |
| 3.7.x            | 20171201-3.7.x |

## Deploying the Release

In order to deploy the release from this repository, simply issue the following BOSH command:
```
$ bosh -e <your environment> upload-release
```

## Configuring BOSH

To apply the addon, a runtime config entry must be created that will instruct BOSH to apply the addon to instances created by the cf-rabbitmq deployment. The file **runtime-config.yml** has been included and should work most installations. To set this runtime config using this file, issue the following BOSH command:

```
$ bosh -e <your environment> update-runtime-config --name=rabbitmq-delayed-message-exchange-addon runtime-config.yml
```
