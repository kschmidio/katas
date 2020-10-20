# Git branching and merging

## Prerequisites
* Know the basic git commands. A refresher can be found [here](https://github.com/hbons/git-cheat-sheet)
* Refresh git concepts like [working tree, index(staging area) and HEAD](https://stackoverflow.com/questions/3689838/whats-the-difference-between-head-working-tree-and-index-in-git)
* [git reset](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset)
* [merging and rebasing](https://www.atlassian.com/de/git/tutorials/merging-vs-rebasing)
* [rebasing can be quite dangerous](https://medium.com/@fredrikmorken/why-you-should-stop-using-git-rebase-5552bee4fed1)

## Steps
### Commit and Reset
1. warmup
   ```
   git init
   touch hello.md
   git add .
   git commit -m "first commit"
   touch kata.md
   git add .
   ```
2. unstage kata.md
   ```
   git reset kata.md
   or
   git reset --mixed HEAD kata.md

   git add .
   git commit -m "second commit"
   ```
3. undo last commit 
   ```
   git reset --hard <GIT_HASH_COMMIT>

   touch kata.md
   git add .
   git commit -m "third commit"
   git log
   ```
4. undo last commit but keep changes
   ```
   git reset HEAD^ (this defaults to --mixed, try the other flags --soft and hard as well)
   ```
5. removes all untracked files
   ```
   git clean -f
   ```
### Create Branch and Merge
1. create new branch and commit a file
   ```
   git branch newFeature
   git checkout newFeature
   or 
   git checkout -b newFeature
   touch newFeature.md
   git add .
   git commit -m "newFeature"
   ```
2. switch back to master and add file
   ```
   git checkout master
   touch master.md
   git add .
   git commit -m "added new file to master"
   ```
3. update newFeature branch with changes from master
   ```
   git checkout newFeature
   git merge master
   ```
4. merge new branch into master
   ```
   git checkout master
   git merge newFeature
   ```
5. delete newFeature branch
   ```
   git branch -d newFeature
   ```
### Create Branch and Rebase
1. create newFeature branch
   ```
   git branch newFeature
   git checkout newFeature
   or 
   git checkout -b newFeature
   touch newFeature.md
   git add .
   git commit -m "newFeature"
   ```
2. switch back to master and add file
   ```
   git checkout master
   touch master.md
   git add .
   git commit -m "added new file to master"
   ```
3. update newFeature branch with changes from master
   ```
   git checkout newFeature
   git rebase
   ```
4. merge newFeature branch into master
   ```
   git checkout master
   git merge newFeature
   ```
5. delete newFeature branch
   ```
   git branch -d newFeature