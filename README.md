Route53 DDNS
============

Linux DDNS Updater for AWS Route53

Setup
-----

Place the files in your system and edit `aws_secrets` with your IAM keys and `run.sh` to configure the Hosted Zone ID and subdomain.

IAM Policy
----------

The following policy is needed in order to update the IP Address properly.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1398798645000",
      "Effect": "Allow",
      "Action": [
        "route53:ChangeResourceRecordSets"
      ],
      "Resource": [
        "arn:aws:route53:::hostedzone/HOSTEDZONEID"
      ]
    }
  ]
}
```

You have to replace `HOSTEDZONEID` by the Hosted Zone ID of your domain.