---
tags: [ssh]
title: ssh
created: '2019-07-30T06:19:49.245Z'
modified: '2019-08-02T07:37:52.091Z'
---

# ssh

`secure shell`

```sh
ssh -T git@github.com         # test ssh-connection

ssh -t  # Force pseudo-terminal allocation.

ssh -i /Users/user/.ssh/google_compute_engine # use different identity file

ssh -p PORT user@host         # connects specified port
```
[Connecting to GitHub with SSH - User Documentation](https://help.github.com/articles/connecting-to-github-with-ssh/)

## options
```sh

-o ServerAliveInterval=60 -o ServerAliveCountMax=120   # 120 x 60

-o StrictHostKeyChecking=no

-o LogLevel=ERROR # QUIET, FATAL, ERROR, INFO, VERBOSE, DEBUG, DEBUG1, DEBUG2, and DEBUG3


-o CheckHostIP=no
-o HostKeyAlias=compute.1407099891930101147 
-o IdentitiesOnly=yes 
-o StrictHostKeyChecking=no 
-o UserKnownHostsFile=/Users/user/.ssh/google_compute_known_hosts 
```

[ssh_config(5) - LogLevel](http://man.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man5/ssh_config.5?query=ssh_config#LogLevel)



### don't read from stdin

`-n` Redirects stdin from /dev/null (actually, prevents reading from stdin).  This must be used when ssh is run in the background.

```sh
while read node; do ssh -n docker@${node} 'uptime'; done
```
[Shell script while read line loop stops after the first line - Stack Overflow](https://stackoverflow.com/a/13800476)

[ssh - How to fix warning about ECDSA host key - Super User](https://superuser.com/a/421024/341187)