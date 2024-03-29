# PasswordLess Login using ssh on both server

Configuring passwordless logins between 2 Linux systems

Process basically involves generating a public authentication key and appending it to the remote hosts `~/.ssh/authorized_keys` file

Note: if it's one side login without password then, just generate and share the key to other server.

Eg. Server-1 should be able to login to server-2 then, generate key on server-1 and pass it to server-2. It will allow server-1 to login to server-2 without any pasword.

## Generate authentication key

If an SSH authentication-key file does not exist, generate one by running the ssh-keygen command. When prompted for a passphrase, use a blank passphrase if fully password-less login is required:

```bash
# ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/user/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/user/.ssh/id_rsa.
Your public key has been saved in /home/user/.ssh/id_rsa.pub.
The key fingerprint is:
1e:b2:f4:89:5a:7f:2d:a5:a5:4d:6d:66:2c:82:d8:18 root@remote-host
```

## Create directories and provide permissions

#### On server 1

```bash
sudo -u {server_1_user} mkdir -m 750 /home/{server_1_user}/.ssh
sudo -u {server_1_user} ssh-keygen -f /home/{server_1_user}/.ssh/id_rsa  -t rsa -b 4096 -N ""
```


#### On server 2

WARNING: Give proper `.ssh` locations

```bash
sudo -u {server_2_user} mkdir -m 750 -p /var/lib/postgresql/.ssh
sudo -u {server_2_user} ssh-keygen -f /var/lib/postgresql/.ssh/id_rsa  -t rsa -b 4096 -N ""
```

## Exchange the public keys generated between the servers

#### On server 1

```bash
cat ~/.ssh/id_rsa.pub | ssh {server_2_user@server_2_ip_address} "cat >> ~/.ssh/authorized_keys"
```

#### On server 2

```bash
cat ~/.ssh/id_rsa.pub | ssh {server_1_user@server_1_ip_address} "cat >> ~/.ssh/authorized_keys"
```

## Test the passwordless connection as follows:

```bash
sudo -u {server_1_user} ssh {server_2@server_2_ip_address}
sudo -u {server_2_user} ssh {server_1@server_1_ip_address}
```