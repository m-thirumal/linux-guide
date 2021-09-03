# Create cron for specific user

    sudo -u postgres crontab -e

## Possible Error:

    /etc/cron.allow: Permission denied
    You (postgres) are not allowed to use this program (crontab)
    See crontab(1) for more information

---Solution

    sudo chmod 644 cron.allow

---- Add user name in `cron.allow`


## Check Cron log

    grep CRON /var/log/syslog

## Troubleshoot

No MTA installed, discord output

install the following packages

    1. sudo apt-get install postfix
    2. sudo apt install mailutils


Use mail to read the `cron job failed message`