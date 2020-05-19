# docker-cron

## Usage
- Add the crontab file to `/var/spool/cron/crontabs/root`.
- Set `TZ` environment variable if you use except UTC.

```
# crontab example
* * * * * echo 'stdout' >&1
* * * * * echo 'stderr' >&2
```

``` Dockerfile
# Dockerfile example
FROM hoto17296/cron

ENV TZ "Asia/Tokyo"
ADD crontab /var/spool/cron/crontabs/root
RUN chmod 644 /var/spool/cron/crontabs/root
```
