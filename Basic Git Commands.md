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
`git revert is` a very powerful command
You can use it to unstage what is in the index
```
git revert
```

You can use this to prune a remote that was locally cached but doesn't exist anymore. 
```
git remote prune origin
```

# reset
`git reset is` a very powerful and meanwhile dangerous command
You can use it to unstage what is in the index
Undo add
```
edit                                     
git add frotz.c filfre.c
mailx                                    
git reset                                
git pull git://info.example.com/ nitfol
```

           1. You are happily working on something, and find the changes in these files are in good order. You do not
           want to see them when you run "git diff", because you plan to work on other files and changes with these
           files are distracting.
           2. Somebody asks you to pull, and the changes sound worthy of merging.
           3. However, you already dirtied the index (i.e. your index does not match the HEAD commit). But you know
           the pull you are going to make does not affect frotz.c or filfre.c, so you revert the index changes for
           these two files. Your changes in working tree remain there.
           4. Then you can pull and merge, leaving frotz.c and filfre.c changes still in the working tree.



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
# you may need to use -D which is the shortcut for --delete --force when the branch you want to delete haven't fully merged in its upstream branch, or not in HEAD if no upstream was set with --track or --set-upstream-to.
git branch -D branch_name
git push remote --delete branch_name # delete a remote branch
```


# checkout a remote branch and create corresponding local branch (--set-upstream)
```
$ git checkout --track origin/newsletter
Branch newsletter set up to track remote branch newsletter from origin.
Switched to a new branch 'newsletter
```

# to clean worktree untracked file
```
# use -n option to preview what will be removed if run git clean -f
git clean -n
git clean -f
# for directory
git clean -n -d 
git clean -f -d
```

# if you want to get the up-to-date information of your remote repo, you can use `git remote update`. by default, it update all the branches.
```
git remote update
```

