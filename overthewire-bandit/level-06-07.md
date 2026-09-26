# Bandit 6 → 7

```console
$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
$ cat /var/lib/dpkg/info/bandit7.password
<REDACTED>
```

`find /` with `-user`/`-group` and `2>/dev/null` to hide errors