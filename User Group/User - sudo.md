# Create user with bash shell and sudo permission

### Add user with home directory & bash shell

```bash
sudo useradd -s /bin/bash -d /home/{home directory} -m {user name}

sudo useradd -s /bin/bash -d /home/thirumal -m thirumal
```
    
### Add user without home directory

```bash
sudo useradd -r -s /bin/false {USERNAME}
```

### Add bash shell

```bash
sudo chsh -s /bin/bash {userName}

sudo chsh -s /bin/bash thirumal
```

### Make `sudo` user

```bash
sudo usermod -aG sudo {username}

sudo usermod -aG sudo thirumal
```

### Change pass

```bash
sudo passwd {userName}

sudo passwd thirumal
```

### Enable `SSH` login for the user

  Open `sudo vi /etc/ssh/sshd_config` and modify the following

  1. To enable password authentication, uncomment

```bash
#PasswordAuthentication yes
```

  2. To enable root login, uncomment

```bash
#PermitRootLogin yes
```

  3. To enable ssh key login, uncomment

```bash
#PubkeyAuthentication yes
#AuthorizedKeysFile .ssh/authorized_keys
```

  4. Add user name in 

```bash
AllowUsers thirumal ubuntu
```

  After modification, restart ssh:

```bash
sudo service ssh restart
```


### Delete User

#### To Delete user

```bash

userdel {username}

userdel thirumal
```

#### To Delete user with home directory

```bash
userdel -r {username}

userdel -r thirumal
```

#### To delete all the files which owns by the user

```bash
sudo killall -u {username}

sudo killall -u thirumal
```

### Password

[To change/enable/disable/aging password](./passwd.md)


