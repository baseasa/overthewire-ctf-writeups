# Bandit 31 → 32

```console
$ git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
$ cd repo
$ cat .gitignore
*.txt
$ echo 'May I come in?' > key.txt
$ git add -f key.txt
$ git config user.name  "bandit31"
$ git config user.email "bandit31@overthewire.org"
$ git commit -m "add key.txt"
$ git push origin master
...
remote: Well done! Here is the password for the next level:
remote: <REDACTED>
...
```

`git add -f` bypasses `.gitignore`, a server-side pre-receive hook can validate pushes and act on them