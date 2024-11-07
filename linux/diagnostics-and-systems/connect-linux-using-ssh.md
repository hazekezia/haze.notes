# Connect Linux using SSH

Just using this simple command.

```bash
ssh username@ip_address
```

Or, if your linux using custom port, use this command.

```bash
ssh -p 11000 username@ip_address
```

* `ssh`: Initiates the SSH connection.
* `-p 11000`: Specifies the custom port `11000` (instead of the default port `22`).
* `<username>`: Replace this with the actual username you want to connect as.
* `<ip_address>`: Replace this with the IP address of the server.
