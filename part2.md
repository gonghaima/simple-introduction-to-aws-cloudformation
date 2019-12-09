![part 1](images/part2.png)

# A Simple Introduction to AWS CloudFormation Part 2: EC2 Instance and Route53

This is a continuation of A Simple Introduction to AWS CloudFormation.

We will build on top of the first simple CloudFormation template from Part 1, which provisions an EC2 instance and Security Group. We will add to it a Route53 record that points to the EC2 instance’s DNS public hostname. This demonstrates CloudFormation’s ability to “orchestrates” the components of the stack. CloudFormation will wait until the EC2 instance’s DNS public hostname is ready and then create the Route53 record pointing to it.

NOTE: All the source code for this post is available on Github: [tongueroo/cloudformation-examples](https://github.com/tongueroo/cloudformation-examples).
