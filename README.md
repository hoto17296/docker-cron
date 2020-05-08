# docker-cron

## Usage
- Mount the crontab file to `/var/spool/cron/crontabs/root`.
- Set `TZ` environment variable if you use except UTC.

```
# crontab example
* * * * * echo 'stdout' >&1
* * * * * echo 'stderr' >&2
```

``` yml
version: '3'

services:

  cron:
    image: hoto17296/cron
    environment:
      TZ: Asia/Tokyo
    volumes:
      - ./crontab:/var/spool/cron/crontabs/root
```