# Bandit 15 → 16

```console
$ openssl s_client -connect localhost:30001
...
Verify return code: 18 (self-signed certificate)
---
<REDACTED>
Correct!
<REDACTED>
closed
```

`openssl s_client` is netcat-over-TLS, the self-signed cert warning is expected here