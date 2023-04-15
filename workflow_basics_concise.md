# Git Collaboration Workflow Basics (with little explanation)
## Based on a feature branch model

#### Start ALL branches from the latest 'main' code:
```
git checkout main
git fetch origin 
git reset --hard origin/main
```
#### Set up a new branch for each new feature or feature update
```
git checkout -b <new-feature-name-convention>
```
#### Add, commit and push as normal from feature branch
```
git status
git add .
git commit -m "changes"
git push -u origin <feature-branch-name>
```
#### Pull requests and reviews
Pull 'main' before a PR
```
git checkout main
git pull origin main
git checkout <feature-branch-name>
```
Respond to suggestions and edit requests before completing PR

