# eip-rotator

<img src="https://github.com/younsl/box/blob/main/box/assets/pink-container-84x84.png" alt="pink container logo" width="84" height="84">

## Description

This script rotates the [Elastic IP address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) of the instance to avoid rate limit of 3rd party service (e.g. Slack, Discord, etc.).

This project is inspired by [maxharlow/aws-ip-rotator](https://github.com/maxharlow/aws-ip-rotator).

## Prerequisites

### IAM Permissions

The following permissions are required to run the script.

- `ec2:ReleaseAddress`
- `ec2:AllocateAddress`
- `ec2:DescribeAddresses`
- `ec2:AssociateAddress`

### CLI tools

The following CLI tools are required to run the script.

- [AWS CLI](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/index.html): Battle-tested 2.25.13 version in production EC2 instance, so recommended to use awscli 2.25.13 or later.

## Usage

### Install

Download raw script file in current directory.

```bash
curl -O https://raw.githubusercontent.com/younsl/eip-rotator/main/eip-rotator.sh
```

Add eip-rotator schedule to crontab.

```bash
sh eip-rotator.sh start
crontab -l
```

Remove eip-rotator schedule from crontab.

```bash
sh eip-rotator.sh stop
crontab -l
```

### Manual run

Or you can run the script manually.

```bash
sh eip-rotator.sh
```