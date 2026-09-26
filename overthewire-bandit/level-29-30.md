# Bandit 29 → 30

```console
$ git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
$ cd repo
$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
$ git log -p remotes/origin/dev
...
 - username: bandit30
-- password: <no passwords in production!>
+- password: <REDACTED>
```

`git branch -a` lists remote branches, secrets often hide off `master`