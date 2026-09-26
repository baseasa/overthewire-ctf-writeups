# Bandit 13 → 14

```console
$ ls
sshkey.private
$ ssh -i sshkey.private bandit14@localhost
$ cat /etc/bandit_pass/bandit14
<REDACTED>
```

SSH can authenticate with a key file (`-i`), every level's own password is readable at `/etc/bandit_pass/<user>` once you're that user