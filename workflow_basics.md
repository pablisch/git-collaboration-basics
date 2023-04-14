# Git Collaboration Workflow Basics
## Based on a feature branch model

NO code is written on the main branch.
ALL code is written on a feature branch related to a single feature.
Use an agreed naming convention, e.g. <status>/<dev-initials>/<feature>
Example: new/pj/user-repository or update/pj-qr/login-page

ALL feature branches should start from the latest main code (from [Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)):
```
git checkout main
git fetch origin 
git reset --hard origin/main
```
Explanation (courtesy of chat.openai.com):
`git checkout main` - This switches the local repository to the main branch.

`git fetch origin` - This retrieves the latest changes from the origin remote repository. It does not merge the changes into the local repository.

`git reset --hard origin/main` - This resets the local main branch to match the origin/main branch. The --hard option discards any changes made locally and resets the branch to match the remote repository.
