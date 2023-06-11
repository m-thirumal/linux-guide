# How to find the virus?

1. Use `htop` to find the virus and running on which user?

2. Check `cron` file for all user, it might have the virus start job.

```bash
sudo -u postgres crontab -e
sudo -u ubuntu crontab -e
```

3. Remove the job from `crontab`.