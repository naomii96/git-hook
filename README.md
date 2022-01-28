# git-hook

Git hooks are scrips that run automatically every time a particular event occurs in a Git repository.
They let you customize Git's internl behavior an trigger customizable actions at key points 
in the development life cycle.

Git Hooks reside under .git/hooks/ of every git repo. Git automatically populates this directory
with example scripts when you initialize a repository.

To “install” a hook, all you have to do is remove the .sample extension. Please note you can create
a new file with the same name minus the .sample, and also change the permission for the file to +x
this allows the file to be an execuable:

`chmod +x pre-commit`

