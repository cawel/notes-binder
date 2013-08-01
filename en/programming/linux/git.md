# git

```
git rebase -i @{u}
```
The “u” stands for “upstream” (added in git v1.7.0), and it resolves to the latest commit on this branch on the remote. Putting it simply, this command rewrites only the local commits which you’re about the push. Starting in git v1.7.6, @{upstream} is the default for when there is no argument.

This gives you a chance to perform basic housekeeping before sharing your changes, such as squashing related commits together and rewording commit messages if they’re too long or not descriptive enough.

This is useful to *rewrite* local history (before you pushed your changes). The philosophy behind this is: don’t make bugs or typos a part of your project’s history if you haven’t shared them yet.

```
git merge --no-ff feature
```
The --no-ff flag ensures there will always be a merge commit, even when technically not necessary. Merge commits are useful because they convey the following information:

* where do changes come from (in this case: the “feature” branch);
* when were the changes merged and by whom, possibly indicating a code review (if that’s part of your development process);
* keeps commits related to this feature/topic grouped together.


git add --all # new and modified files
git add "*.txt" # all text files in all project
git add *.txt # add text files in current dir



if you forgot something on a commit
git reset --soft HEAD^
* undo last commit, and put changes into staging
* will move the HEAD pointer to the previous commit (and set the HEAD to that commit)

git reset --hard HEAD^
* undo last commit and all its changes (nothing is put into staging)

untrack and does not delete from local repo
```
git rm --cached <file>

## to deploy to heroku
* Heroku only deploys the remote master branch, so if we want to deploy another local branch, we go:
```
git push heroku staging:master


## tags
list all tags
```
git tag
```

checkout a tag
```
git checkout v0.0.0.1
```

tag a commit
```
git tag -a v0.0.3 -m "description"
```

push the tags on the remote
```
git push --tags
```

list tracked/stale branches
```
git remote show 
```

delete stale branches for a specific remote ('origin' in this case)
```
git remote prune origin
```

custom log
```
git config --global alias.mylog "log --pretty=format:'%h %s [%an]' --graph"

set email for current repo (not global)
```
git config user.email me@example.com
```

sets an alias for the "git status" command
```
git config alias.st status

split a commit

```
git rebase -i
```
and then 'edit', git reset HEAD^, do 1st commit, do 2nd commit