# Connect Linux using SSH

Just using this simple command.

```bash
ssh username@ip_address
```

Or, if your linux using custom port, use this command.

```bash
ssh -p port_number username@ip_address
```

* `ssh`: Initiates the SSH connection.
* `-p port_number`: Specifies the custom port (instead of the default port `22`).
* `<username>`: Replace this with the actual username you want to connect as.
* `<ip_address>`: Replace this with the IP address of the server.

***

**Connect to Linux server without password (SSH key)**

Generate SSH key. Select the default location (`~/.ssh/id_rsa`) and leave the password blank for automatic access.

```bash
ssh-keygen -t rsa -b 4096
```

Then copy your SSH key to linux target.

```bash
ssh-copy-id -p port_number username@ip_address
```
