# SES SMTP credentials by converting existing AWS credentials

You need an Amazon SES SMTP user name and password to access the Amazon SES SMTP interface. You can use the same set of SMTP credentials in all AWS regions.

But your AWS access key ID and secret access key are different and will not work for SES sending emails. 

This python script can generate SMTP password from IAM user's secret access key. The SMTP user name is the same as the AWS access key ID, so you only need to generate the SMTP password.

**Usage:**  python main.py your-access-secret aws-region-name

Make sure IAM user have below permissions:

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "ses:SendRawEmail",
            "Resource": "*"
        }
    ]
}
