# Create user with bash shell and sudo permission

### Add user with home directory & bash shell

    sudo useradd -s /bin/bash -d /home/{home directory} -m {user name}

    sudo useradd -s /bin/bash -d /home/thirumal -m thirumal

### Add bash shell

    sudo chsh -s /bin/bash {userName}

    sudo chsh -s /bin/bash thirumal

### Make `sudo` user

    usermod -aG sudo {username}

    usermod -aG sudo thirumal

### Change pass

    passwd {userName}

### Enable `SSH` login for the user

  Open `vi /etc/ssh/sshd_config` and modify the following

  1. To enable password authentication, uncomment

    #PasswordAuthentication yes

  2. To enable root login, uncomment

    #PermitRootLogin yes

  3. To enable ssh key login, uncomment

    #PubkeyAuthentication yes
    #AuthorizedKeysFile .ssh/authorized_keys

  4. Add user name in 

    AllowUsers thirumal ubuntu

After modification, restart ssh:

    sudo service ssh restart
