# test-first-repository
Testing git commands in command-line - will be updated when I learn something new or fix up gaps in my understanding of git!

- [test-first-repository](#test-first-repository)
  * [Github Basics](#github-basics)
    + [Setting up repo](#setting-up-repo)
    + [Clone repo locally](#clone-repo-locally)
    + [Updating files](#updating-files)
    + [Regular routines](#regular-routines)
    + [Repo cycle](#repo-cycle)
    + [Branching](#branching)
    + [Pull requests](#pull-requests)
    + [Updating branches and keeping up with master](#updating-branches-and-keeping-up-with-master)
    + [Making changes on the wrong branch](#making-changes-on-the-wrong-branch)
    + [Git merge vs rebase](#git-merge-vs-rebase)

## Github Basics
Basics that combine both the commandline and website.

### Setting up repo
- Go to profile on web -> Repositories -> New (green button)
- Name repo and write a short description
- Initialise the repository with a README
- Navigate to the web page of the created repo, click the Code (green button) and copy the link under Clone with HTTPS

### Clone repo locally
- Open terminal and navigate to the folder to store your repositories (use `cd` and `ls` commands to navigate directories and list contents)
- Use `git clone <url>` to place repo in the desired directory
- Use `git status` to show whats different between local and cloud files

### Updating files
- When you've edited and changed your files in your repo locally, use `git add <filename>` to add/update single files or `git add -A` to add/update all files in the local repo to cloud.
- To actually update, use `git commit -m <message>`
- The message can be about the changes you've made or on features that you've worked on
- If you use `git commit` without a message, press escape and enter `:wq` to save it

### Regular routines
Should use `git pull` - pulls new changes to the local repo and `git push` - push new changes to cloud repo, at least twice an hour to sync progress especially working in group/team projects

### Repo cycle
Pull -> Add -> Commit -> Push

### Branching
- Use `git pull` to update the master branch
- use `git branch` to list all active branches in the repo
- Use `git branch <branch-name>` to create a copy of your master branch under the `<branchname>`
- A `<branchname>` should be a new feature added or something that you've modified
- Use `git checkout <branch-name>` to switch and start working on the desired branch
- This will not affect anything on the master branch

### Pull requests
- Use `git checkout master` to switch to master branch
- Use `git pull` to update changes
- Use `git checkout <branch-name>` to switch batch to the branch working on
- Use `git merge master` to request merge back to `<branchname>` branch
- If successful, use `git push`
- Go back to the webpage of the repo and create a pull request
- Get a team member to review and create the merge request

## Commandline commands 
Documenting commands to help myself work in group projects!

| Command                       | Details and Explaination                                                                                                              |
| ------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `git clone <url>`             | clone an existing repo onto local machine                                                                                             | 
| `git status`                  | shows state of branch alongside changes to files                                                                                      | 
| `git add <file-name>`         | adds/tracks the modified file to be ready to commit                                                                                   | 
| `git commit -m <message>`     | commit the changes with a message to be ready to push                                                                                 | 
| `git commit`                  | commit the changes to be ready to push                                                                                                | 
| `git push`                    | push all commits from local repo to cloud repo                                                                                        | 
| `git pull`                    | pull all changes from cloud repo to local repo                                                                                        | 
| `git branch`                  | shows current branch and local branches                                                                                               | 
| `git branch <branch-name>`    | create a new branch                                                                                                                   | 
| `git branch -d <branch-name>` | delete existing local branch                                                                                                          | 
| `git checkout <branch-name>`  | switch to desired branch                                                                                                              | 
| `git merge <branch-name>`     | merge branch to desired branch                                                                                                        | 
| `git merge --abort`           | undo merge conflicts                                                                                                                  | 
|                               | can also try `git revert HEAD` which reverts reference to last commit in current branch (use `cat .git/HEAD` in commandline to see)   | 
| `git stash`                   | save the modifications made to files in repo locally (temporary)                                                                      |          | `git stash apply`             | apply the modifications made to files in repo locally                                                                                 |
| `git log`                     | shows a list of commits displaying messages and users that were made                                                                  |
| `git rebase`                  | apply a 'cleaner merge' to a branch by placing the commits on the source branch to the target, as if the commits were made in the     |
|                               | target in the first place (WARNING - DOESN'T PRESERVE HISTORY, USE MERGE IF UNSURE)                                                                          

## Key lessons that I paid a price for

### Updating branches and keeping up with master
Branch maintenance is key in managing multiple branches for multiple features. In order to not let branches get too behind:
- Use `git checkout <branch-name>` to access branch that is needed to be caught up
- Use `git pull` to sync any changes on the branch
- Use `git merge master` to pull master into branch
- Use `git push` to push and update branch to achieve the same status as master

### Making changes on the wrong branch
If you've messed up and modified files in the wrong branch and need to switch to another (ie. modified master but meant to do it in game-patches)
- Use `git stash` to save changes made in modified files
- Use `git checkout <branch-name>`
- Use `git merge master` to make sure if checkouted branch is not out of date
- Use `git stash apply` to apply those changes to branch (will still have to add, commit and push)

### Git merge vs rebase
A merge preserves the branch history, rebase doesn't. A merge should be use on public branches as the history of the commits made are important. A history of contributions made by other users should be preserved. A rebase should be use on private branches or on personal branches exclusively as it 'rewrites history' and leaves no trace, as if it always was on the master branch. If you're unsure, always merge! 
