# Create cron for specific user

```bash
sudo -u postgres crontab -e
````

## Possible Error:

```bash
/etc/cron.allow: Permission denied
You (postgres) are not allowed to use this program (crontab)
See crontab(1) for more information
```

#### Solution:-

1. Create `cron.allow` in `/etc`, if it's not found

```bash
sudo touch /etc/cron.allow
```

2. Add permission
    
```bash
sudo chmod 644 cron.allow
```

3. Add user name `thirumal` in `cron.allow`


## Check Cron log

```bash
grep CRON /var/log/syslog
```

## Troubleshoot

No MTA installed, discord output

install the following packages

```bash
sudo apt-get install postfix
sudo apt install mailutils
```


Use mail to read the `cron job failed message`