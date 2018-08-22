# Bosh release for amazon-ssm-agent for Ubuntu Xenial

If you need the [Amazon SSM Agent](https://docs.aws.amazon.com/systems-manager/latest/userguide/ssm-agent.html) product in your infrastructure then deploy this BOSH release.

## Usage

### Install BOSH CLI

Only tested with bosh-cli version 3.0.1

### Create & Upload the BOSH release

To use this BOSH release, first create the dev release, then the final release, then upload it to your BOSH director:

```
bosh target BOSH_HOST
git clone https://github.com/dashaun/bosh-amazon-ssm-agent-xenial
cd bosh-amazon-ssm-agent-xenial
wget https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/debian_amd64/amazon-ssm-agent.deb
bosh add-blob ./amazon-ssm-agent.deb amazon-ssm-agent.deb
bosh create-release --force
bosh create-release --force --final
bosh upload-release
```

