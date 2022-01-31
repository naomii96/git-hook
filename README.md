# git-hook

Git hooks are scrips that run automatically every time a particular event occurs in a Git repository.

Git events just to name a few:
- push
- commit 
- rebase
- pull 

They let you customize Git's internl behavior and trigger customizable actions at key points 
in the development life cycle.

Git Hooks reside under .git/hooks/ of every git repo. Git automatically populates this directory
with example scripts when you initialize a repository.

ls .git/hooks 
``` 
applypatch-msg.sample     pre-commit.sample         prepare-commit-msg.sample
commit-msg.sample         pre-merge-commit.sample   push-to-checkout.sample
fsmonitor-watchman.sample pre-push.sample           update.sample
post-update.sample        pre-rebase.sample
pre-applypatch.sample     pre-receive.sample
```

To “install” a hook, all you have to do is remove the .sample extension. Please note you can create
a new file with the same name minus the .sample, and also change the permission for the file to +x
this allows the file to be an execuable:

`chmod +x pre-commit`

