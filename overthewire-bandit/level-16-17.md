# Bandit 16 → 17

```console
$ nmap -sV -p 31000-32000 localhost
...
PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
31691/tcp open  echo
31790/tcp open  ssl/unknown
31960/tcp open  echo

$ ncat --ssl localhost 31790
<REDACTED>
Correct!
-----BEGIN OPENSSH PRIVATE KEY-----
<PRIVATE KEY REDACTED>
-----END OPENSSH PRIVATE KEY-----

$ chmod 600 sshkey.private
$ ssh -i sshkey.private bandit17@bandit.labs.overthewire.org -p 2220
$ cat /etc/bandit_pass/bandit17
<REDACTED>
```

`nmap -sV` finds and fingerprints services, `ncat --ssl` talks to the TLS one, private keys must be `chmod 600` or SSH refuses them