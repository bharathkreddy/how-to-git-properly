# how-to-git-properly
my notes on how to use git and version control properly.

1. The Perfect Commit
  - Commit only files and changes relating to a single topic.
  - Do not cram all changes in one commit. 
  - use staging area wisely and choose files and changes to commit. 
  - never do ```git add .``` or ``` git add -A```
  
2. Compose a good Commit 
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
  
RESOURCES :
  [Fully automated version management and package publishing](https://github.com/semantic-release/semantic-release)
  [Commit lint](https://github.com/conventional-changelog/commitlint)
  [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)
  [scemantic versioning](https://semver.org/)
