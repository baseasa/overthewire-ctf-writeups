# Bandit 20 → 21

```console
#terminal 1 :
$ nc -lvnp 12345
Listening on 0.0.0.0 12345
Connection received on 127.0.0.1 37826
<REDACTED>          
<REDACTED>          

#terminal 2 :
$ ./suconnect 12345
Read: <REDACTED>
Password matches, sending next password
```

classic listener + client dance, `nc -l` listens, the setuid client reads what you serve and hands back the reward