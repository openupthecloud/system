## Git + GitHub

`git` is a command-line tool, and [GitHub](https://github.com/) is a company built on the underlying git technology. `git` is the open-source library (that can be found here: https://github.com/git/git). Git allows you to return to previous versions of a codebase, allowing many engineers to collaborate on a codebase without "breaking" each others work. You can think of it like a fancy file + folder system for code. Around ~75% of companies use GitHub + Git is their primary version control system. Alternatives to Git + GitHub are: SVN, Gerrit, AWS CodeCommit. 

| Roles that should know                                                                                                                                                             | Roles that are nice to know                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| [DevOps](/roles/devops-engineer.md), [Cloud Engineers](/roles/cloud-engineer.md), [Backend Engineer](/roles/backend-engineer.md), [Frontend Engineer](/roles/frontend-engineer.md) | [Support / Helpdesk](/roles/support-helpdesk.md), [Quality Assurance Engineer](/roles/quality-assurance-engineer.md) |

### Key Concepts

1. Branches + Pull Requests (GitHub)
1. Commits ("Save") + Tags (Version)
3. "Branch Strategy" (see: [GitHub Flow](https://i0.wp.com/lanziani.com/slides/gitflow/images/gitflow_1.png) + [Basic Flow](https://littlekendra.com/images/release-flow.png))
 
### Exercise 1: Learning the git basics

#### What you'll learn

Install Git + begin to explore the following commands in a Linux environment. If you need a Linux environment, you can use the [Open Cloud Dev Box](https://github.com/openupthecloud/open-cloud-dev-box).

**The basic way of using git**

1. `git add file.txt` => Tells git to prepare to be committed.
2. `git commit -m "a message"` => Saves the change.
3. `git push` => Syncs the change with GitHub.

**Useful commands**

* `git status` => This is "home base" on your current state. 
* `git push --set-upstream origin garcia-adding-search-feature` => Pushes a local branch to remote GitHub. 

#### Example Scenario

1. You are an employee asked to "make a website for clothing". 
1. Go and create the clothing website `repo`. 
1. Your first task is to create a "homepage". 
1. Create a `branch` for your new task and add a `homepage.txt`. 
1. `Push` the changes and open a pull request. 
1. Comment your own pull request as your "colleague", who asks you to add an image to the homepage.
1. Add a file "image.txt" and update the "homepage.txt" content. 
1. `Commit` and push this change. 
1. Review your pull request. 
1. Approve the pull request. 
1. `Merge` the pull request. 
 
*Repeat the above until you feel comfortable!*