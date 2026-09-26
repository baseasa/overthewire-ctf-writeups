# Bandit 19 → 20

```console
$ ls -la
...
-rwsr-x---   1 bandit20 bandit19 14880 Jun 24 14:58 bandit20-do
$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
$ ./bandit20-do cat /etc/bandit_pass/bandit20
<REDACTED>
```

a setuid-root/other binary runs with the file owner's privileges — here it reads a file you otherwise can't