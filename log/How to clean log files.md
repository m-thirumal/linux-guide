# How to clean log files

## Check the disk space (files and folders)

Check the disk space from the command line. Use the `du` command to see which files and directories consume the most space inside of the `/var/log` directory.

```bash
du -h /var/log/

ls -l -h
```

### Empty the log file

Use the `cat` command (concatenate) to empty the log files or directories.

```bash
cat /dev/null > deamon.log
```

- `/dev/null` is a non-existent file with no information.

- When you concatenate `/dev/null` to a log file, you empty the file data, but do not delete the file name.

