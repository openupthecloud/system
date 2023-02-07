# Linux + CLI

Learning to navigate the terminal and terminal CLI is a valuable skill for almost every cloud role. Here are some basic information and exercises to start to build your comfort and proficiency with the command line. If you need a Linux environment to work in, check out the [Open Cloud Dev Box](https://github.com/openupthecloud/open-cloud-dev-box). 

| Roles that should know                                                                                                                                                             | Roles that are nice to know                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| [DevOps](/roles/devops-engineer.md), [Cloud Engineers](/roles/cloud-engineer.md), [Backend Engineer](/roles/backend-engineer.md), [Frontend Engineer](/roles/frontend-engineer.md) | [Support / Helpdesk](/roles/support-helpdesk.md), [Quality Assurance Engineer](/roles/quality-assurance-engineer.md) |


## Exercise 1: Navigating directories + files

The first important thing to learn about Linux is how to navigate the file system and manipulate files. Explore and play around with the following commands. Remember that you can run `man` before a command to read instructions on how to use the command. For instance: `man ls` to understand the `ls` command. 

* `pwd` => Prints the context of where you are, it stands for "print working directory".
* `cd` => Changes the current directory. 
* `cp` => Copies a file
* `touch` => Creates a file (or updates an existing file).
* `ls` => List the current directory.
* `mkdir` => Make a directory.
* `mv` => Move a file.
* `rm` => Removes a file.

Linux systems use a "shorthand" for navigating the file system. These are called _"relative"_ and _"absolute"_ file paths. A relative path is (as implied) relative to where you're currently located. Absolute file paths are based on the overall structure of the system. Experiment with the commands `cd ../` to navigate "up one step in the directory structure. `cd /` to go to the "root" of the directory structure. Or `cd /some/path/to/a/directory`. See ([relative + absolute paths for more](https://linuxhint.com/absolute-relative-paths-linux/)).

**Using only the command line:**

**Scenario:** You are tasked with creating directories for three "employees" of a company. Follow the steps below to create the directories and relevant files. 

1. Create three directories named after employees: "Sarah", "Clark", "Anika".
2. Change directory into one of the employees directory.
3. Create a file "employee-details.txt"
4. Copy that file into each of the other directories. 

**Bonus**

1. Create a shell script taking 1 argument (the name), which creates a directory for each employee.

## Exercise 2: Your first shell script

This exercise is to create a script that simply emits the string "hello world". In setting up the script you should get familiar with the syntax of a "shebang" in Linux, and using the `chmod` command to alter file permissions. 

1. `touch cloud-resume-challenge.sh` => Create a file 
   - `ls` => Check if the file exists
2. `chmod u+x cloud-resume-challenge.sh` => Adds executable permissions
3. `#!/bin/sh` => Add the "shebang" to the top of a shell script 
4. `echo "hello world"` => Add scripts to the file !

## Exercise 3: Advanced shell script

To understand the relevancy of shell scripting, let's do something "real". For this exercise we're going to take on step 4 of the cloud resume challenge, using the AWS CLI.

> Your HTML resume should be deployed online as an Amazon S3 static website. Services like Netlify and GitHub Pages are great and I would normally recommend them for personal static site deployments, but they make things a little too abstract for our purposes here. Use S3. -  [Cloud Resume Challenge](https://cloudresumechallenge.dev/docs/the-challenge/aws/)

Following ths guide ([AWS S3 Static Website Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html)), complete the following steps to create a static site on S3 using the command line. By the end you should be able to delete the S3 bucket, and re-create using a single command shell script. 

1. Created a shell script (updated permissions `chmod` + "shebang")
2. Created an S3 bucket in S3
2. Update the S3 bucket to ensure it's a "static site"
3. Update the S3 bucket policy so your site can be publically accessed
4. Create a local directory using `mkdir` and add an "index.html" file to the directory
5. Sync the local directory with S3 to "upload" your file

Some useful links: 

- [AWS CLI - S3](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/index.html)
- [AWS CLI - S3API](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3api/index.html)

**Bonus**

1. Update the script to use a variable, rather than repeating the name
2. Find a way to update `policy.json` to remove the hardcoded reference to the bucketname
3. Add an `error.html`, not just `index.html`
4. Break down the scripts into two (one for creating the bucket, one for syncing the files)

## Further reading

- [Shell Scripting Tutorial](https://www.shellscript.sh)
