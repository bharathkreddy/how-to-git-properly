# how-to-git-properly
my notes on how to use git and version control properly.

### 1. The Perfect Commit
  - Commit only files and changes relating to a single topic.
  - Do not cram all changes in one commit. 
  - use staging area wisely and choose files and changes to commit. 
  - never do ```git add .``` or ``` git add -A```
  
### 2. Compose a good Commit 
  - Header : <type>[optional scope]: Description
    - Types of commits can be
    - feat – a new feature is introduced with the changes
    - fix – a bug fix has occurred
    - chore – changes that do not relate to a fix or feature and don't modify src or test files (for example updating dependencies)
    - refactor – refactored code that neither fixes a bug nor adds a feature
    - docs – updates to documentation such as a the README or other markdown files
    - style – changes that do not affect the meaning of the code, likely related to code formatting such as white-space, missing semi-colons, and so on.
    - test – including new or correcting previous tests
    - perf – performance improvements
    - ci – continuous integration related
    - build – changes that affect the build system or external dependencies
    - revert – reverts a previous commit
  - Body : Detailed description covering
    >A properly formed Git commit subject line should always be able to complete the following sentence: If applied, this commit will **your subject line here**
    - Why have I made these changes?
    - What effect have my changes made?
    - Why was the change needed?
    - What are the changes in reference to?
  - Optional footer
  
---

# GIT COMMANDS
  
### 1. Installing Git
    + sudo apt-get update
    + sudo apt-get install Git
  
### 2. Verifying the installation
    + git --version

### 3. Configuring the username and email ID
    + git config --global --list
    + git config --global user.name "Username"
    + git config --global user.email "Email"

### 4. Change the defaultbranch name of the Main from Master use:
    + git config --global init.defaultBranch main

### 5. Innitialize repo
    + git init

### 6. Move the file from untracked/unstaged to staged area
    + single file= git add <file name>
    + multiple files=  git add .

### 7. Commit 
    + New file= git commit -m "message"
    + modified file= git commit -am "message"

### 8. Remote Repo
    + Connect Local repo with Remote repo: git remote add origin <repo url>
    + Verify remote connections: git remote -v
    + Remove remote repo: git remote remove <name of the remote repo>

### 9. Log commands
    + Commit list in details= git log
    + Commit list in one line= git log --oneline
    + List of all the authors within the project (s=summary and n = numbered) = git shortlog -s -n
    + Commits list by author= git log --author <Author Name>
    + OR = git log --author=<2/3 starting letters>
    + Logs of specific file= git log --author <Author Name> <filename>
    + Logs for a specific file= git log -p <fileName>
    + Decorated view of log= git log --all --decorate --oneline --graph
    + OR= git log --graph --oneline
    + Log view of specific commit= git show <comitid> --stat
    + View last few commits= git log -<no of commits you want to view>
    + View logs between specific dates= git log --after <date> --before <date>
    + Detailed view of logs in one line= git log --stat --oneline
    + To read the total count of commits in the repo: git log --oneline | wc -l
    + To view the backend log with even the hidden steps we can use: git reflog

### 10. Renameing a file from git
    + git mv <old name> <new name>

### 11. View the list of configuration
    + git config --global --list

### 12. Alias:
    + git config --global alias.br branch
    + git config --global alias.ci commit
    + git config --global alias.st status
    + git config --global --unset "alias.name"
    + git config --global --unset-all

### 13. Diff commands:
    + Difference between two commits= git diff <old commit> <new commit>
    + Modified VS Commited = git diff <filename>
    + Staged VS Commited = git diff --staged <Filename>
    + Staged VS Specific Commit = git diff <commit ID>
    + Remote VS Local = git diff origin/master

### 14. Pushing Changes to remote Repo
   + 1st time push= git push -u origin <remote branch>
    + multiple times push= git push

### 15. Cloning a repo
    + Complete repo= git clone <URL of the repo>
    + Only a branch from the repo= git clone -b <Branch name><Repository URL>

### 16. View List of Files
    + List all files – git ls-files
    + List stagged files – git ls-files --stage
    + List of file in a directory – git ls-files --directory <dir name>

### 17. Configure git ignore to your system
    + git config --global core.excludesFile <PATH TO .GITGNORE FILE>

### 18. Checkout Commands:
    + To switch to a branch = git checkout <branchname>
    + To switch to a remote branch = git checkout <remotebranch>
    + To switch to a commit git checkout commitid
    + To switch to a tag git checkout tagname


### 19. Clean Command
  + To view the implication of the clean command - Git clean -–dry-run
  + To force delete the file from the repo - Git clean -f
  + To delete dir - Git clean -f -d
  + To delete all the files and dir - Git clean -f -d
  + To delete all the ignored file in one go - Git clean -f -x
  + To delete all the files and dir incliding ignored files - Git clean -f -d -x

### 20. RM Command
  + Removes the file from the git and the file system - git rm -f <filename>
  + Removes the file only from git repo but actual file will still be there in the project – git rm --cached <filename>

### 21. Reset Command
  + Move the file to Staging area= git reset --soft <commit-id> 
  + Move the file to unstaged area= git reset --mixed <commit-id> 
  + Move the files out of records or reverts the file to the stage of previous commited stage git reset --hard <commit-id>

### 22. Revert Command
  + git revert <commitID>
  + Note:- when you want to revert from 5th commit to 3rd commit then pass the commit id of 4th Commit to revert to the 3rd commit stage.

### 23. Amend Command
  + git commit --amend -m “message”

### 24. Tag Command
  + Annotated tag= git tag -a <tagname> <commit-id> -m "Message here"
  + Lightweight tag= git tag <tag name> <commit-id>
  + Get the list of tags= git tag --list
  + Get the list of tags with their messages= git tag -n
  + Delete a tag= git tag -d <tagname>
  + View a specific tag= git show <tagname> 
  + Pushing tags to remote repo= git push --tags
  + Delete tag from remote= git push --delete origin <tagname>

### 25. Stashing Commands
  + To show the list of files stashed – git stash list
  + To stash all the files – git stash
  + To show the latest stash or files stashed at 0th position – git stash show
  + To show the stashed records at position 1 – git stash show {1} or use git stash show <stash@{0}>.
  + To stash with a message – Git stash save “message”
  + To get the files back to work – Git stash pop
  + To get back the stashed files at position 1 – Git stash pop {1}
  + This will remove the files from the position 1 and it will also delete the change completely and u cannot undo this – Git stash drop {1} / {stash-id}
  + Remove all the stashed files in one go – Git stash clear
  + Stash Show more details= git stash show -p
  + Stashing a single file= git stash -- <filename>

### 26. Git Branching
  +	I want to see the branches available in this repository then: Git branch
  +	I want to see all the branches including local and remote branches: Git branch -a
  +	I want to see all the branches and their last/latest commits along with their message: Git branch -v
  +	Delete a branch: Git branch <branchname> -d 
  +	Rename a branch: Git branch -m  <oldName> <newName>
  +	If you are on the branch you want to rename: git branch -m new-name
  + to check the parent of a branch = git log -g <branch name>
  + To view only the remote branch list: git branch -r
  + To create a branch and move inside the newly created branch in one go: git checkout -b <branch name>

### 27. Git Merging
  + git merge

### 28. git rebase
  + git rebase

### 29. Change the default branch
  + git push --set-upstream origin <branchname>

---

# RESOURCES :
  1. [Fully automated version management and package publishing](https://github.com/semantic-release/semantic-release)
  2. [Commit lint](https://github.com/conventional-changelog/commitlint)
  3. [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)
  4. [scemantic versioning](https://semver.org/)
  5. [codecov](https://about.codecov.io/)
  6. [commitizen](https://github.com/commitizen/cz-cli)
