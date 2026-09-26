# Bandit 28 → 29

```console
$ git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
$ cd repo
$ git log -p
...
 - username: bandit29
-- password: <REDACTED>
+- password: xxxxxxxxxx
```

`git log -p` shows every change ever made, removing a secret in a new commit does NOT remove it from history