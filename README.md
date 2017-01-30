# XVT CloudFront IP Update

This role will create a Lambda function which then subscribes to the `AmazonIpSpaceChanged` SNS topic. This topic
receives periodic updates regarding AWS' public IP namespace(s). These updates are utilised by the Lambda function to
update Security Group (SG) inbound rule tables.

You would need to use this role in the event you're using CloudFront to restrict access to an ELB and the resources it
manages, but only want CloudFront talking to the ELB (the alternative in `0.0.0.0/0`)

## Requirements

Utilises AWS services, so boto will be needed, an AWS account, and for certain security groups to be pre-existing.

## Role Variables

N/A

## Dependencies

N/A

## Example Playbook

```yaml
- hosts: servers
  roles:
     - { role: xvt-cloudfront-ips }
```

## License

Copyright XVT

## Author Information

Michael Crilly <michael.crilly@xvt.com.au>
