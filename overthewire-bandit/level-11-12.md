# Bandit 11 → 12

```console
$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is <REDACTED>
```

ROT13 is a Caesar cipher, `tr` does the substitution