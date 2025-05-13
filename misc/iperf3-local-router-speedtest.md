---
icon: wifi
---

# Local Speedtest using iperf3

### Objective

To measure the actual network throughput between two devices connected to the same local router using `iperf3`.

***

### What is iPerf3?

**iPerf3** is a command-line tool for measuring network bandwidth. It works using a client-server model and can test both upload and download speeds across TCP and UDP protocols.

***

### Requirements

* Two devices connected to the same local network (wired or wireless)
* `iperf3` installed on both devices
* Access to a terminal or command prompt

***

### Installation

#### Ubuntu/Debian

```bash
sudo apt update
sudo apt install iperf3
```

#### macOS (Homebrew)

```bash
brew install iperf3
```

#### Android (Termux)

```bash
pkg install iperf3
```

#### Windows

Download from: [https://iperf.fr/iperf-download.php](https://iperf.fr/iperf-download.php)

***

### Test Setup

iPerf3 operates with one device as the **server** and the other as the **client**.

***

### Step-by-Step Test

#### 1. Start the Server

On Device A (e.g., your laptop or Raspberry Pi):

```bash
iperf3 -s
```

This will start the iPerf3 server and wait for incoming connections.

***

#### 2. Run the Client

On Device B, determine the IP address of Device A, then run:

```bash
iperf3 -c <server_ip_address>
```

Example:

```bash
iperf3 -c 192.168.1.10
```

This runs a default 10-second test from client to server.

***

#### 3. Test in Reverse (Optional)

To test bandwidth from server to client:

```bash
iperf3 -c 192.168.1.10 -R
```

***

### Understanding the Results

* Focus on the **Bandwidth** column (in Mbits/sec).
* The value represents the actual throughput between the devices.
* Expect variations based on Wi-Fi vs Ethernet, signal strength, and router quality.

***

### Additional Options

| Option         | Description                         |
| -------------- | ----------------------------------- |
| `-t <seconds>` | Change test duration (default: 10s) |
| `-P <number>`  | Use multiple parallel connections   |

Examples:

```bash
iperf3 -c 192.168.1.10 -t 30
iperf3 -c 192.168.1.10 -P 4
```

***

### Conclusion

iPerf3 is a simple yet effective tool to test the real network speed between two devices on the same local network. It helps identify potential bottlenecks in routers, cables, or wireless connections.
