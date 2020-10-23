### What is a User?

• Every process (running program) runs as particular user

• Every file is owned by particular user

• File and directory access are restricted by user

• User associated with running process determines files and directories that process can access

```
    thirumal@thirumal:/home$ sudo adduser user2 --home  /home/user2home
    Adding user `user2' ...
    Adding new group `user2' (1004) ...
    Adding new user `user2' (1003) with group `user2' ...
    Creating home directory `/home/user2home' ...
    Copying files from `/etc/skel' ...
    Enter new UNIX password:
    Retype new UNIX password:
    passwd: password updated successfully
    Changing the user information for user2
    Enter the new value, or press ENTER for the default
            Full Name []: User2
            Room Number []: 25
            Work Phone []: 8973697871
            Home Phone []:
            Other []:
    Is the information correct? [Y/n] y
    enkindle@production:/home$ ls -l
    total 16
    drwxr-xr-x 19 jessica  jessica  4096 May 16 15:23 jessica
    drwxr-xr-x  2 thirumal thirumal 4096 May 16 15:45 thirumal
    drwxr-xr-x  2 user1    user1    4096 May 16 15:45 user1
    drwxr-xr-x  2 user2    user2    4096 May 16 15:49 user2home
  ```
Create user with home directory

	usermod thirumal -m

#### Viewing User Information
• To view info for current logged-in user, use id

   ○ To view info about another user, add username as first argument


        ```
        [student@desktop1 ~]$ id
        uid=1000(student) gid=1000(student) groups=1000(student),10(wheel) context=unconfined_u:nconfined_r:unconfined_t:s0-s0:c0.c1023
            • To list user associated with file or directory, use ls -l
        [student@server1 ~]$ ls -l /tmp
        drwx------. 2 gdm     gdm      4096 Jan 24 13:5 orbit-gdm
        drwx------. 2 student student  4096 Jan 25 20:0 orbit-student
        -rw-r--r--. 1 root    root    23574 Jan 24 13:5 postconf
	 ```

• To view process information, use ps

   ○ To view all processes, use a option

   ○ To view user associated with process, use u option

    [student@server1 ~]$ ps au
    USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
    root       428  0.0  0.7 152768 14400 tty1     Ss+  Feb03   0:4 /usr/bin/Xorg
    root       511  0.0  0.0 110012   812 ttyS0    Ss+  Feb03   0:0 /sbin/agetty
    root      1805  0.0  0.1 116040  2580 pts/0    Ss   Feb03   0:0 -bash
    root      2109  0.0  0.1 178468  2200 pts/0    S    Feb03   0:0 su - student
    student   2110  0.0  0.1 116168  2864 pts/0    S    Feb03   0:0 -bash
    student   3690  0.0  0.0 123368  1300 pts/0    R+   11:2   0:00 ps au

User/UID Mapping

• Output of id, ls -l, and ps display username

• OS tracks users by UID, not name

• Names/UID mapping stored in /etc/passwd

• Map uses flat-file with seven colon-separated fields per user:

username:password:UID:GID:GECOS:/home/dir:shell

    Field	Description
    username	Mapping of a UID to a name for the benefit of human users.
    password	Historically, passwords were kept here in encrypted format. Today they are stored in a separate file called /etc/shadow.
    UID	        User ID, the number that identifies the user at the most fundamental level.
    GID	        The user’s primary group ID number. Groups are discussed next.
    GECOS	    Arbitrary text field, usually includes the user’s real name.
    /home/dir	The location of the user’s personal data and configuration files.
    shell	    A program that runs as the user logs in. For a regular user, this is normally the program that provides the user’s command line prompt.
