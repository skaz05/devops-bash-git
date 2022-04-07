# Version Control
Git is a tool for managing changes in projects on which multiple people work. We use git to store our code, scrips, configs and a team can efficiently track changes and adapt to them.

## Git basic overview

- Create a "repository" (project) with a git hosting tool (like Github, Gitlab, Bitbucket)
- Clone repositories to your local machine
- Add files to your local copy of the repo and "commit" (save) the changes
- "Push" your changes to the main branch
- "Pull" changes made by others to your local machine
- Create a "branch", make changes, commit and push them
- Open a "pull request", others can review your changes and decide if they are ok
- "Merge" your branch to the main branch


### Practice
- create a repo in your github account
- clone the repo on your machines (```git clone <repo_url>```)
- add a new file, commit and push it
  - ```git status```
  - ```git add <file>```
  - ```git commit -m "always add a relevant message"```
  - ```git push origin master```
- create a new branch on github in your repo
- fetch the new branch on your local and checkout
  - ```git fetch```
  - ```git checkout <new_branch>```
- make some changes, add a new file
  - ```git status```
  - ```git add <file>```
  - ```git commit -m "always add a relevant message"```
  - ```git push origin <new_branch>```
- merge your changes, you can create a pull request and request review
  - you can also pull the <new_branch> onto master and push it without review
     - ```git checkout master```
     - ```git pull [origin] <new_branch>```
     - ```git push origin master```