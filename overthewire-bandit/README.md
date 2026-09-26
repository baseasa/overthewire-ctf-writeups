# OverTheWire — Bandit Writeup

my solutions and notes for the [OverTheWire Bandit](https://overthewire.org/wargames/bandit/) wargame, levels **0 → 33** (all levels completed)

bandit teaches the Linux command line and the fundamentals you need for the rest of the OverTheWire games: file handling, permissions, SSH, networking tools, basic crypto/encoding, cron, and git

> **No passwords here.** OverTheWire asks players not to publish passwords or spoilers. Every level password in this repo is shown as `<REDACTED>`. The writeups explain the *method* — the actual flags stay on my machine.

## connection info

```bash
ssh bandit<N>@bandit.labs.overthewire.org -p 2220
```

- host: `bandit.labs.overthewire.org`
- port: `2220`
- level 0 password: `bandit0`

## level info

| Level | Concept | Key command / tool |
|------:|---------|--------------------|
| [0 → 1](level-00-01.md) | reading a file | `cat` |
| [1 → 2](level-01-02.md) | awkward filename (`-`) | `cat ./-` |
| [2 → 3](level-02-03.md) | spaces in filename | quoting / `./` |
| [3 → 4](level-03-04.md) | hidden files | `ls -a` |
| [4 → 5](level-04-05.md) | finding the human-readable file | `file`, `find` |
| [5 → 6](level-05-06.md) | finding by size/attributes | `find -size` |
| [6 → 7](level-06-07.md) | finding by owner/group | `find -user -group` |
| [7 → 8](level-07-08.md) | searching text | `grep` |
| [8 → 9](level-08-09.md) | unique line | `sort \| uniq -u` |
| [9 → 10](level-09-10.md) | readable strings in binary | `strings` |
| [10 → 11](level-10-11.md) | base64 | `base64 -d` |
| [11 → 12](level-11-12.md) | ROT13 | `tr` |
| [12 → 13](level-12-13.md) | nested compression | `xxd`, `gzip`, `bzip2`, `tar` |
| [13 → 14](level-13-14.md) | SSH private key | `ssh -i` |
| [14 → 15](level-14-15.md) | plain TCP | `nc` |
| [15 → 16](level-15-16.md) | TLS TCP | `openssl s_client` |
| [16 → 17](level-16-17.md) | port scan + TLS | `nmap`, `ncat --ssl` |
| [17 → 18](level-17-18.md) | diffing files | `diff` |
| [18 → 19](level-18-19.md) | hostile `.bashrc` | remote `ssh` command |
| [19 → 20](level-19-20.md) | setuid binary | `./bandit20-do` |
| [20 → 21](level-20-21.md) | setuid daemon + listener | `nc -l`, `./suconnect` |
| [21 → 22](level-21-22.md) | cron job | reading `/etc/cron.d` |
| [22 → 23](level-22-23.md) | cron + predictable filename | `md5sum` |
| [23 → 24](level-23-24.md) | cron runs your script | shell script drop |
| [24 → 25](level-24-25.md) | brute-forcing a PIN | bash loop + `nc` |
| [25 → 26](level-25-26.md) | escaping a pager | `more` / `vi` trick |
| [26 → 27](level-26-27.md) | setuid via editor | `vi` shell escape |
| [27 → 28](level-27-28.md) | git clone | `git clone` |
| [28 → 29](level-28-29.md) | git history | `git log -p` |
| [29 → 30](level-29-30.md) | git branches | `git branch -a` |
| [30 → 31](level-30-31.md) | git tags | `git tag`, `git show` |
| [31 → 32](level-31-32.md) | git push | `git push` |
| [32 → 33](level-32-33.md) | scaping a restricted shell | `$0` |
| [33](level-33.md) | end of game | — |

## what i learned

- comfort navigating and searching a Unix filesystem under awkward conditions (weird filenames, hidden files, permission walls)
- `find` as a swiss-army knife: by size, owner, group, permissions
- encoding vs. encryption: base64, ROT13, and layered compression formats
- networking with `nc`, `openssl s_client`, `ncat --ssl`, and `nmap`
- privilege escalation basics: setuid binaries, world-writable cron targets, predictable temp paths
- git as a place secrets hide: history, branches, tags, and pre-receive hooks
- restricted-shell escapes via pagers, editors, and `$0`
