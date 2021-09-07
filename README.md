## SNMP monitoring using Amazon CloudWatch and Elastic Logstash

Read the blog about this application: 

### Prerequisites for deploying the solution with AWS CloudFormation
To deploy the example application, you need the following:

- Permissions in your AWS account to create the resources. This example uses admin credentials.

- A VPC with a public subnet or a private subnet with a route to a NAT gateway.

- An EC2 keypair.

### Deployment
This template creates EC2 instances, CloudWatch custom metrics and related resources. You will be billed for the AWS resources used if you create a stack from this template.
 
1.	On the AWS CloudFormation console, choose Create stack.
2.	Choose the option to use new resources.
3.	Upload the saved template file.
4.	For Stack name, enter a name for the stack.
5.	For network configuration, select an existing VPC and one subnet with internet access.
6.	For EC2 Configuration, leave defaults for demo, or adjust Logstash instance type to match Logstash JVM size.
7.	For troubleshooting and connectivity, enter your SSH location IP CIDR and select an existing EC2 key pair.
8.	Choose Next.
9.	Step through the remaining pages.
10.	On the final page, select the acknowledgement that IAM resources can be created.
11.	Choose Create stack. It takes approximately 10 minutes to complete.

This stack creates one EC2 instance for the Logstash server and two instances running the SNMP daemon, fully configured with cfn-init helper scripts. The deployment also creates a secret with a randomly generated password in AWS Secrets Manager, the necessary EC2 IAM profiles and locked down security groups.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

