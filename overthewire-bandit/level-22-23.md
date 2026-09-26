# Bandit 22 → 23

```console
$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash
myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget

$ mytarget=$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
$ echo $mytarget
8ca319486bfbbc3663ea0fbe81326349
$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
<REDACTED>
```

predictable filenames = predictable secrets, Reproduce the derivation to find the drop location
