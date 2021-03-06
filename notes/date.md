---
tags: [coreutils]
title: date
created: '2019-07-30T06:19:49.033Z'
modified: '2021-02-23T16:28:36.890Z'
---

# date

> print or set the system date and time

## install
`brew install coreutils`

## usage
```sh
# get string format
man strftime                      
#   %F    is equivalent to "%Y-%m-%d"
#   %k    is replaced by the 24-hour as decimal number (0-23); single digits are preceded by a blank

# flags
# -u, --utc, --universal    print or set UTC (=Coordinated Universal Time)

date "+%s"                        # get unix timestamp
date "+%F_%T"                     # 2020-01-30_13:16:52
date "+%F_%H-%M"                  # 2020-01-30_13-16
date +"%m-%d-%y_%H-%M"            # mont day year, hour minute

date -r "1563533492792"           # convert unix timestamp on bsd/macos
gdate -d "@1563533492792"         # convert unix timestamp on linux

date -u -d "$(date -d "8am")"     # convert local time to UTC

date -d "$(date -u -d "10am")"    # convert UTC time to local

date -v -11d                      # subtract 11 days from current date on bsd/macos

# calculate days difference
echo "$(( (  $(gdate "+%s") - $(gdate -d "2020-10-13T08:30:10+00:00" "+%s") )/(60*60*24) ))" 
```

## see also
- [[hwclock]]
- [[timedatectl]]
- [[strftime]]
- [[cal]]
