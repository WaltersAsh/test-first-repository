# test-first-repository
Testing git commands in command-line!

## Github Basics
Revising commands to help myself work in group projects

Common commands
- `git clone <url>`            clone an existing repo onto local machine
- `git status`                 shows state of branch alongside changes to files 
- `git add <filename>`         adds the modified file to be ready for commit
- `git commit -m <message>`    commit the changes with a message
- `git commit`                 commit the changes to be ready for push
- `git push`                   push all commits from local repo to cloud repo
- `git pull`                   pull all changes from cloud repo to local repo
- `git branch`                 shows current branch and local branches
- `git branch <branchname>`    create a new branch
- `git branch -d <branchname>` delete existing local branch 
- `git checkout <branchname>`  switch to desired branch            
- `git merge master`           merge master to current branch

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
- Use `git branch <branchname>` to create a copy of your master branch under the `<branchname>`
- A `<branchname>` should be a new feature added or something that you've modified
- Use `git checkout <branchname>` to switch and start working on the desired branch
- This will not affect anything on the master branch

### Pull requests
- Use `git checkout master` to switch to master branch
- Use `git pull` to update changes
- Use `git checkout <branchname>` to switch batch to the branch working on
- Use `git merge master` to request merge back to `<branchname>` branch
- If successful, use `git push`
- Go back to the webpage of the repo and create a pull request
- Get a team member to review and create the merge request

