![part 4](images/cloudformation-part4.png)

# A Simple Introduction to AWS CloudFormation Part 4: Change Sets = Dry Run Mode

I am a big fan of AWS CloudFormation because it gives you the power to codify the infrastructure and provision it in a repeatable way. One thing that I’ve always wished that CloudFormation had was the ability to see the what changes would be applied ahead of time before hitting that update-stack button. Who wants to hit a big scary red button without knowing what is about to happen? I don’t.

In the puppet world, this preview run is called dry-run or noop mode. In terraform world, this is known as a terraform plan. In response, the AWS team has released something called [Change Sets](https://redirect.viglink.com/?format=go&jsonp=vglnk_157653381123611&key=0d3176c012db018d69225ad1c36210fa&libId=k48z9yq80102jk33000DA14qq0f8d25et&subId=90a093a441eeed5ed87cea10819eb718&cuid=90a093a441eeed5ed87cea10819eb718&loc=https%3A%2F%2Fblog.boltops.com%2F2017%2F04%2F07%2Fa-simple-introduction-to-aws-cloudformation-part-4-change-sets-dry-run-mode&v=1&out=https%3A%2F%2Faws.amazon.com%2Fblogs%2Faws%2Fnew-change-sets-for-aws-cloudformation%2F&title=A%20Simple%20Introduction%20to%20AWS%20CloudFormation%20Part%204%3A%20Change%20Sets%20%3D%20Dry%20Run%20Mode%20-%20BoltOps%20Blog&txt=Change%20Sets).

When I first heard of Change Sets, the name made me think of git changesets. I assumed that this meant I would have to write a “change set” and then apply this change set to the CloudFormation stack. The same way a git patch file can be applied to your source code. This sounded like a lot of work and not what I was looking for. But I’ve had a chance to look at change sets recently, and my understanding of them was completely wrong. CloudFormation Change Sets is dry run mode! It’s AWS way of generating a preview of what the stack update will do. This is exactly what I’ve been looking for.

NOTE: All the source code for this post is available on Github: [tongueroo/cloudformation-examples](https://github.com/tongueroo/cloudformation-examples).

