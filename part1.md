# Part 1: EC2 Instance

If are using AWS and want to automate creating resources you should look into AWS CloudFormation.

NOTE: All the source code for this post is available on Github: tongueroo/cloudformation-examples.
Stories in the series:

1. [A Simple Introduction to AWS CloudFormation Part 1: EC2 Instance](https://blog.boltops.com/2017/03/06/a-simple-introduction-to-aws-cloudformation-part-1-ec2-instance)
2. [A Simple Introduction to AWS CloudFormation Part 2: EC2 Instance and Route53](https://blog.boltops.com/2017/03/20/a-simple-introduction-to-aws-cloudformation-part-2-ec2-instance-and-route53)
3. [A Simple Introduction to AWS CloudFormation Part 3: Updating a Stack](https://blog.boltops.com/2017/03/24/a-simple-introduction-to-aws-cloudformation-part-3-updating-a-stack)
4. [A Simple Introduction to AWS CloudFormation Part 4: Change Sets = Dry Run Mode](https://blog.boltops.com/2017/03/24/a-simple-introduction-to-aws-cloudformation-part-3-updating-a-stack)

# What is CloudFormation?

The easiest way to describe what CloudFormation is that it is a tool from AWS that allows you to spin up resources effortlessly. You define all the resources you want AWS to spin up in a blueprint document, click a button, and then AWS magically creates it all. This blueprint is called a template in CloudFormation speak.

CloudFormation makes sure that dependent resources in your template are all created in the proper order. For example, let’s say we want to create a DNS Route53 record and a EC2 instance having the DNS record point to the EC2 instance. CloudFormation will take care to provision the EC2 instance first, wait for that to be ready, and then create the DNS record afterwards. AWS CloudFormation “orchestrates” the provisioning of the desired resources.

So instead of having to write script with a bunch of AWS API calls, wait loops, and retry logic, you just tell describe what you want and tell CloudFormation to do it for you. Beautiful.

