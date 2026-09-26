# Bandit 5 → 6

```console
$ cd inhere
$ find -size 1033c ! -executable -type f
./maybehere07/.file2
$ cat ./maybehere07/.file2
<REDACTED>
```

`find` filters on size (`c` = bytes) and permission attributes
