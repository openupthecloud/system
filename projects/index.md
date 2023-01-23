
# Choosing A Project

| Project Name                                          | Suitable for Beginners? |
| ----------------------------------------------------- | ----------------------- |
| [Cloud Resume Challenge](./cloud-resume-challenge.md) | Yes                     |
| [Cloud Dev Environment](./cloud-dev-environment.md)   | Yes                     |
| [Adrian Cantrill Labs](./adrian-cantrill-labs.md)     | Yes                     |


**Useful Resources**
- [Udemy DevOps Projects Course](https://www.udemy.com/course/devopsprojects/?src=sac&kw=devops+projects)
- [TechChak](https://www.techchak.com/)
- [Darey](https://www.darey.io/)


## Building Basic Skills

Before you dive into a project, you'll probably need to understand Git and GitHub. 

## Git / GitHub

### Why Git? What is Git?

* `git` command-line tool `github` the company 
* `git` is the open-source library (found here: https://github.com/git/git)
* Around ~75% of companies use GitHub + Git is primary VCS
* Alternatives to Git + GitHub are: SVN, Gerrit, AWS CodeCommit.
* Allows you to Return to a previous version of an application

### Key Concepts

* Branches, Pull Request (GitHub), Commits ("Save"), Tags (Version)
* "Branch Strategy"
  * [GitHub Flow](https://i0.wp.com/lanziani.com/slides/gitflow/images/gitflow_1.png)
  * [Basic Flow](https://littlekendra.com/images/release-flow.png)
 
### Who needs to know Git?

* **Should know (e.g. uses git day-to-day)**: DevOps, Cloud Engineers, Software Engineers (front-end, back-end).
* **Nice to have (e.g. not using day-to-day)**: Solutions Architect, Cloud Support.

### Main things to know

**The simple + basic flow**

1. `git add file.txt` => Tells git to prepare to be committed.
2. `git commit -m "a message"` => Saves the change.
3. `git push` => Syncs the change with GitHub.

**Useful other commands**

* `git status` => This is "home base" on your current state. 
* `git push --set-upstream origin garcia-adding-search-feature` => Pushes a local branch to remote GitHub. 

### Things to practice

1. Create a repo (e.g. a website)
2. Create a branch (e.g. `task-1`)
3. Add files, modify files, delete files
4. Commit changes
5. Push changes
6. Raise pull requests, merge pull requests

**Take the following scenario:** 
* You are an employee asked to "make a website for clothing". 
* Go and create the clothing website `repo`. 
* Your first task is to create a "homepage". 
* Create a `branch` for your new task and add a `homepage.txt`. 
* `Push` the changes and open a pull request. 
* Comment your own pull request as your "colleague", who asks you to add an image to the homepage.
* Add a file "image.txt" and update the "homepage.txt" content. 
* `Commit` and push this change. 
* Review your pull request. 
* Approve the pull request. 
* `Merge` the pull request. 
 
Repeat the above until you feel more comfortable! 

## Docker

Depending on the project you're building

**Practice:**
1. Installing the `docker` CLI on your machine
1. Pulling a docker image from DockerHub
1. Writing your own Dockerfile

**Resources:**
- [Docker Tutorial for Beginners - A Full DevOps Course on How to Run Applications in Containers](https://www.youtube.com/watch?v=fqMOX6JJhGo)
- [Learn To Cloud Guide - Phase 4: DevOps Fundamentals](https://learntocloud.guide/#/phase4/README) 

## Shell scripting

**Practice:**
1. Writing a short shell script
2. Try to: print a strings
3. Try to: do basic arithmatic, e.g. addition, subtraction

**Resources:**
- [Learn To Cloud Guide - Phase 1: Linux Bash and Networking fundamentals](https://learntocloud.guide/#/phase1/README?id=phase-1-linux-bash-and-networking-fundamentals)
- [Bash scripting will change your life](https://www.youtube.com/watch?v=7qd5sqazD7k)

