# Bandit 12 → 13

```console
$ mkdir -p /tmp/mywork && cp data.txt /tmp/mywork && cd /tmp/mywork
$ xxd -r data.txt > archive       

$ file archive
archive: gzip compressed data, was "data2.bin", ...
$ mv archive file.gz && gunzip file.gz && mv file archive

$ file archive
archive: bzip2 compressed data, ...
$ mv archive file.bz2 && bunzip2 file.bz2 && mv file archive

$ file archive
archive: gzip compressed data, was "data4.bin", ...
$ mv archive file.gz && gunzip file.gz && mv file archive

$ file archive
archive: POSIX tar archive (GNU)
$ tar -xf archive        # -> data5.bin
$ tar -xf data5.bin      # -> data6.bin
$ tar -xf data6.bin      # -> data8.bin

$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", ...
$ mv data8.bin file.gz && gunzip file.gz && mv file data8.bin
$ cat data8.bin
The password is <REDACTED>
```

`file` tells you the format at each layer, `xxd -r` reverses a hexdump, formats seen: gzip, bzip2, tar