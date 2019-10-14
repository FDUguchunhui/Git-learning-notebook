Git is really powerful while so complex.

This document will just introduce basic git commands that are enough for personal usage for git beginner.

# add
You can use `add` to add you files into stage area.

## difference between untrack and unstaged
`unstaged` means files have been changed but haven't been added to the stage area
`untrack` means files have been create but don't exist in stage area, i.e. new files

# rm
There are two function of `rm --cached`

The first is more easy to master.
You can use this to remove file from stage area when the file is the same as working tree.

```console
echo 'first line' >> fileA
git rm --cached fileA
```

The second is more complex.
You can simulated a deleted status of a file but not necessarily need to delete that file in working tree when 
the file is the same as what is in the repo.
```
echo 'first line' >> fileA
git commit -a -m 'first line'
git rm -cached fileA
git status # it will show that what is staged is a delete option for fileA while fileA is untracked
```

# revert


# reset



# restore





```
echo 'this is a message > message.txt
git add message.txt
git status
rm --cached message.txt
git status # check whether message.txt is already removed
```





# delete a branch
```
git branch -d branch_name # delete a local branch
git push remote --delete branch_name # delete a remote branch
```
