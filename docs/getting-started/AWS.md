# Autopilot <> AWS

Autopilot is an orchestration service that provisions an Elasticsearch cluster on your AWS account. For doing this, it needs to access and create EC2 instances on your account.

Autopilot can do this through AWS's [IAM (Identity and Access Management)](https://aws.amazon.com/iam/), which allows fine-grained access to AWS APIs without any overhead. 

Configuring an IAM user for Autopilot is a one-time process that should take less than 10 minutes.

## Video Walkthrough

The video below shows how to configure an IAM user with the necessary permissions for Autopilot in 1 min.

[![Youtube Video for IAM](https://i.imgur.com/Hdwsmld.png)](https://vimeo.com/180582772)

Alternatively, you can follow the direct steps listed below to the same effect.

## Direct Steps

We will set up the IAM user and link it to Autopilot dashboard in five easy steps.

#### Step #1. Access the "Security Credentials" tab from your AWS console's dropdown menu where you see your name.
> ![](http://i.imgur.com/CU8bTV3.png?1)  

#### Step #2. Create a new IAM user
> ![](https://i.imgur.com/XO2lNll.png)

#### Step #3. Once the user is successfully created, click "Show Security Credentials".
> ![](https://i.imgur.com/2bSabL8.png)

Copy the ``Acess Key ID`` and ``Secret Access Key`` values, and paste them into Autopilot's **Launch Cluster** tab.
> ![](https://i.imgur.com/cKIq3r2.png)

#### Step 4. By default, a user has no permissions. We will add the permissions for accessing EC2 instances.
> ![](https://i.imgur.com/7hspp35.png)

Click on the **user**.
> ![](https://i.imgur.com/tjr3TP4.png)

Attach ``EC2FullAccess`` policy.
> ![](https://i.imgur.com/LoNiFcN.png)

#### Step #5. Final result
> ![](https://i.imgur.com/Rzezuxz.png)

This is the text that should appear in the policy.
```js
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "ec2:*",
      "Effect": "Allow",
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": "elasticloadbalancing:*",
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": "cloudwatch:*",
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": "autoscaling:*",
      "Resource": "*"
    }
  ]
}
```

Voila! You are all set to deploy clusters with [Autopilot](https://autopilot.appbase.io/login) now.

---
