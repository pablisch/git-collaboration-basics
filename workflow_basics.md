# Git Collaboration Workflow Basics
## Based on a feature branch model

NO code is written on the main branch.
ALL code is written on a feature branch related to a single feature.
Use an agreed naming convention, e.g. `<status>/<dev-initials>/<feature>`

Example: `new/pj/user-repository` or `update/pj-qr/login-page`

### Start branches from the latest main branch code

ALL feature branches should start from the latest main code (from [Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)):
```
git checkout main
git fetch origin 
git reset --hard origin/main
```
Explanation (courtesy of chat.openai.com):

`git checkout main` - Switches the local repository to the main branch.

`git fetch origin` - Retrieves the latest changes from the origin remote repository but does not merge the changes into the local repository.

`git reset --hard origin/main` - This resets the local main branch to match the origin/main branch. The `--hard` option discards any changes made locally and resets the branch to match the remote repository.

Since no chnages should ever be made locally, the `--hard` option is only destructive to something that should not have been done.

### Set up a new branch for each new feature or feature update
```
git checkout -b <new-feature-name-convention>
```
The `-b` flag tells git to create a new branch if it doesn't already exist. It is not needed when moving between existing branches.

### Add, commit and push as normal from feature branch

The feature branch should be used exactly as you would when working on the main except that you will push to `origin <new-branch-name>` instead of `origin main`.

Well thought out commit messages and frequent pushes will help your team know what is going on. Although you may be working on another branch, anything that is pushed is accessible to the whole team on GitHub.
```
git status echo '👉🏻 git 👻  echo '🚀 
git add .
git commit -m "changes"
```
Don't forget to push your commits to the remote repo.
```
git push -u origin <feature-branch-name>
```
The `-u` flag adds the new branch as the remote tracking branch after which `git push` can be used without any parameters.

### Pull requests and reviews

#### WORKFLOW
> pull 'main'      
 
> make pull request
> 
> inform team
> 
> review by team member
> 
> make changes based on review
> 
> commit updates
> 
> pull 'main'
> 
> complete pull request

Pull the latest code from 'main' before making a pull request to limit conflicts during the pull request.
```
git checkout main
git pull origin main
git checkout <feature-branch-name>
```
Then make a pull request and inform the team.
A member of the team should let everyone else know they are responding and the review the PR.
Any suggestions should be acted on, commited and pushed.

If there may have been changes to 'main' since the PR was made, it is worth pulling the latest code from 'main' again before completing the PR.

