---
tags: [linux]
title: locale
created: '2020-03-03T07:13:41.122Z'
modified: '2020-09-09T11:24:46.759Z'
---

# locale

> display locale settings

## usage
```sh
locale -a                                           # lists all public locales.

LC_MONETARY=en_US.UTF-8 locale currency_symbol      # displays `$`


LC_ALL='C'  # C is the default locale, "POSIX" is the alias of "C" - maybe derived from ANSI-C
```

## see also
- [[localectl]]
- [[localedef]]
- [[sw_vers]]
- [unix.stackexchange.com/what-does-lc-all-c-do](https://unix.stackexchange.com/questions/87745/what-does-lc-all-c-do)
