---
tags: [bash/builtin]
title: bash jobs
created: '2019-08-02T06:42:37.604Z'
modified: '2019-08-20T07:21:21.965Z'
---

# bash jobs

> Lists the jobs running in the background, giving the job number

[[bash process-handling]], [[bash fg]], [[bash bg]]


```sh
jobs         # lists all jobs (use with -l to see associated PID)
```

| Notation | Meaning        |
|--        |--              |
| `%N`     | Job number [N] |
| `%S`     | Invocation (command-line) of job begins with string S                   |
| `%?S`    | Invocation (command-line) of job contains within it string S            |
| `%%`     | "current" job (last job stopped in foreground or started in background) |
| `%+`     | "current" job (last job stopped in foreground or started in background) |
| `%-`     | Last job                 |
| `$!`     | Last background process  |
