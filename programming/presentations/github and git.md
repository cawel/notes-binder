
# Git and GitHub Secrets by Zach Holman

## Source video (43 min):
<iframe width="560" height="315" src="http://www.youtube.com/embed/Foz9yvMkvlA?rel=0" frameborder="0" allowfullscreen></iframe>

## Github

* can add .diff & .patch to url's
* add ?w=1 to the url will ignore whitespace
* new default is now HTTPS (no more SSH)
* HTTPS credentials are now cached with git 1.7
* gists are full repos

hub is a superset of git, e.g. 

```
hub git push origin,heroku
```

* add ?author=holman to url to filter commits from a specific user


## Git

```
--allow-empty
```
will allow a commit without committing files


```
git show :/query
```
looks through git log comments for the query and takes the last one


```
git checkout -
```
to switch to the last branch you were in (useful to switch frequently between branches)


```
git fsck --lost-found
```
will show dangling commits


```
git status -sb
```
is more to the point


```
git diff HEAD^ --word-diff
```
useful for English prose


```
git config --global color.ui 1
```

```
git shortlog -sn
```
will show commits grouped by author