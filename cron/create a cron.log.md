# create a `cron.log` file

Create a `cron.log` file to contain just the `CRON entries` that show up in `syslog`. 

Note that CRON jobs will still show up in syslog if you follow the following directions.

Open the file

   `/etc/rsyslog.d/50-default.conf`
  
Find the line that starts with:

   `#cron.*`

uncomment that line, save the file, and restart rsyslog:

   `sudo service rsyslog restart`

You should now see a cron log file here:

   `/var/log/cron.log`
   
Cron activity will now be logged to this file (in addition to syslog).

Note that in `cron.log` you will see entries for when cron ran scripts in `/etc/cron.hourly, cron.daily, etc`. 
