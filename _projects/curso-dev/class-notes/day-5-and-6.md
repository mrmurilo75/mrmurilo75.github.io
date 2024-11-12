---
title: Day 5 & 6 - Git basics
category: class-note
project: curso-dev
date: 2024-11-10
---

> Although this is pretty basics, it is a good starting point to a more comprehensive post on it. 

## Git

Git is a Distributed Version System. It keeps "snapshots" of our folder, which allows us to rollback changes, or merge them with the changes of other people. 

---

Any changes, additions, or deletions that we want to send to git need to be **staged**, with the command `git add FILE [...]`.

Once a change is staged, it can be **committed**. This saves everything that is staged as an new "snapshot", called *commit*, and associates it with a message, using the command `git commit -m $MESSAGE`.

Each *commit* is a point in time that can be rolled back to using `git reset`. There are different hardness to rolling back, depending on wether we want to undo it only the commit or the changes to the file themselves. See the `man` command for more information.

Lastly, we can look at the commited "snapshots" by using `git log`. See the `--stat` for more info; `-N` where N is a number of logs to be shown; and `--oneline` for less information.

To see the change between two commits we can use `git diff`.

To push the staged changes to the last commit (ammend it) we can use `git commit --ammend`. We can also pass a message argument if we want to change it.

When using a remote repository, we can send our local changes to it using `git push`. If our local branch has changes that conflict with the remote, but that we are sure we want to override, we can use the flag `--force` or the short form `-f`.