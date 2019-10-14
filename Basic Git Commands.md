# difference between untrack and unstaged
`unstaged` means files have been changed but haven't been added to the stage area
`untrack` means files have been added to the stage area but those files don't exist in repository, i.e. new files

# delete a branch
```
git branch -d branch_name # delete a local branch
git push remote --delete branch_name # delete a remote branch
```
