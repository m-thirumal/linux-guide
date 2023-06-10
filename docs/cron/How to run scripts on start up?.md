## How to run scripts automatically when Ubuntu starts up?

### Use cron

Running `crontab -e` will allow you to edit your cron.

Adding a line like this to it:

```bash
@reboot /path/to/script >> /var/log/daily-backup.log 2>&1
```

will execute that script once your computer boots up.
