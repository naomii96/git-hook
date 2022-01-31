## git-hook

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

```
ls .git/hooks

```
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

```
chmod +x pre-commit

```

Once all the set up is done, once you run `git commit` or `git commit -m 'message'` this `pre-commmit` script will be executed.

Now you might be asking why you would want to have a hook on your repository, its a fair question. So lets say you have tests that gets triggered every time you build your project and some times these tests fail and now you have to fix the issues and commit and push again. Now thats a lot of work, don't you think?.

Using a hook gives you the ability to trigger the tests on every commit, its a bit of an over kill i guess but I call it being safe.

In my case here [pre-commit](https://github.com/naomii96/git-hook/blob/main/pre-commit.sample) all I wanted to do was perform mvn checkstyle:check before committing.