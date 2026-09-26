# Bandit 4 → 5

```console
$ cd inhere
$ find -type f | xargs file
./-file06: Non-ISO extended-ASCII text, with NEL line terminators
./-file09: data
./-file01: data
./-file08: data
./-file00: data
./-file03: data
./-file07: ASCII text
./-file02: OpenPGP Secret Key
./-file05: data
./-file04: data
$ cat ./"-file07"
<REDACTED>
```

`file` identifies content type regardless of extension, again `./` handles the leading dash

