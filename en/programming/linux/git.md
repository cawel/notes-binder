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