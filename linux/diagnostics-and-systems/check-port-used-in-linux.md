# Check Port Used in Linux

Linux provides several tools that allow you to quickly see which ports are in use and which applications are using those ports.

## netstat

`netstat` is a classic utility that can display network connections, routing tables, and protocol statistics.

```bash
sudo netstat -tuln
```

**Explanation:**

* `-t`: Show TCP connections
* `-u`: Show UDP connections
* `-l`: Show only listening sockets (active ports)
* `-n`: Display addresses in numeric format (skip DNS resolution)

## ss

`ss` is a more modern and faster tool than `netstat` for analyzing socket connections. `ss` displays similar information to `netstat` but with better performance.

```bash
sudo ss -tuln
```

## lsof

`lsof` (list open files) can show detailed information on network ports and the specific processes using them.

```bash
sudo lsof -i -P -n
```

You can specify a specific port to search for processes.

```bash
lsof -i :<port_number>
```

**Explanation:**

* `-i`: Show all network files
* `-P`: Use port numbers instead of names
* `-n`: Skip DNS lookup for faster results

## nmap

If you want to check open ports on your system from an external perspective, `nmap` (network mapper) is a useful tool.

```bash
sudo nmap -sT -O localhost
```

**Explanation:**

* `-sT`: TCP connect scan
* `-O`: Detect the operating system
