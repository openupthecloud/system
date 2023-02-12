# AWS

To get up and running with AWS, you'll need to create an account, and understand a few things about permissions. Here are some instructions and notes on getting set up. 

## Exercise 1: User creation + access credentials

The following steps walk you through how to create an AWS user, get some access credentials, and associate those credentials with your AWS CLI, so you can make CLI calls based on that user. 

1. Create an AWS account + complete the setup
2. Install the AWS CLI on your machine
3. Create a user (call it any name)
4. Create credentials for that user (access key + secret)
5. Add those credentials to the CLI using `aws configure` 
    - Input the access key + secret key.
    - Set region to `us-east-1` 
    - **Why?** You can override the region in the CLI with `--region="us-east-1"`, etc. But, it can get a bit annoying to keep typing, so a default region can be useful. Some regions don't have all the AWS services (you can look this up online). I choose `us-east-1` as some services *ONLY* work in that region also. However, you _can_ choose any region you like. 

> **Warning:** You are not given AWS access credentials twice, so if you lose them, you'll need to re-create some more access credentials. Also, you should NEVER store your credentials in text files, or insecure locations. Also, you should NEVER commit your keys to GitHub or any source control. If you do, delete those access keys immediately (this process is called "key rotation") so they cannot be exploited.

## Applying permissions in IAM

The user created before should have no permissions. The following is a short exercise to get start to understand how IAM works, and permissions are granted to certain entities. To understand IAM, you'll need to understand a few key terms: 

1. `Services` (e.g. This should be quite familiar, it's one of the AWS services, e.g. S3, RDS, EC2, etc)
2. `Actions` (e.g. A "thing" that you're trying to do, e.g. make an S3 bucket, delete an S3 bucket) 
3. `Resources` (e.g. A resource in AWS, typically one that you created, or own)

When you run commands with the AWS CLI and you don't have permissions, the thrown error messages typically tell you the Resource + Actions that you need to configure. Here are two examples: 

1. **Example (listing an S3 bucket)** - Given the error: `An error occurred (AccessDenied) when calling the ListBuckets operation: Access Denied`, `ListBuckets` is the `Action`, the resouce is any/all.  
2. **Example (listing an S3 bucket)** - Given the error: ```make_bucket failed: s3://garcias-bucket-12-02-2023 An error occurred (AccessDenied) when calling the CreateBucket operation: Access Denied``` the `Action` is `CreateBucket`, the `Resource` is `s3://garcias-bucket-12-02-2023`.

## Exercise 2: Exploring IAM permissions

In this exercise you're going to explore and understand policies, resources and actions, and how they affect the permissions you can access from a given entity. In this case, a user entity access AWS via the CLI. 

1. Call `aws s3 ls` without adding permissions for your user
    - ❌ Observe that the command returns permission denied, you don't have permissions to list S3 buckets. 
2. Add an inline policy to our user to grant `ListAllMyBuckets`
    - ✅ Observe success for `aws s3 ls`, you should see all S3 buckets. Let's try and create a bucket
3. Try to create a bucket with `aws s3 mb s3://sams-bucket`
    - ❌ Observe permission denied, you don't have permissions to create buckets, only list. 
3. Add an inline policy for `CreateBucket` for a specific bucket, e.g. `s3://sams-bucket`
    - ✅ Observe success when creating a bucket named `aws s3 mb s3://sams-bucket`
4. Create another bucket called `aws s3 mb s3://garcias-bucket`
    - ❌ Observe permission denied, you only have permissions to act on the previously named resource, let's add it. 
5. Updated the inline policy with `s3://garcias-bucket`
    - ✅ Observe success creating bucket with `aws s3 mb s3://garcias-bucket`

**Bonus**

1. Update inline policy using the wildcard character `*` e.g. `s3://finance-*` to allow the creation of buckets only the buckets prefixed with `finance-`
    - ✅ Observe success for `aws s3 mb s3://finance-october-2020`
    - ❌ Observe failure to create bucket for `aws s3 mb s3://accounting-october-2020`

## FAQ

- **Is this exercise covered in the AWS free tier?** S3 currently charges for bucket content size + retrieval. As of the time of writing, 1 GB of data, with no traffic will cost $0.24 per year. 