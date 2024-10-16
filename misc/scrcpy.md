---
description: pronounced "screen copy"
icon: screencast
---

# Scrcpy

This application mirrors Android devices (video and audio) connected via USB or [over TCP/IP](https://github.com/Genymobile/scrcpy/blob/master/doc/connection.md#tcpip-wireless), and allows to control the device with the keyboard and the mouse of the computer. It does not require any _root_ access. It works on _Linux_, _Windows_ and _macOS_.

Tutorial for ADB over TCP/IP, [here](adb-connect-over-tcp-ip.md).

Just type this command for default mode:

```
scrcpy
```

For docs, [here](https://github.com/Genymobile/scrcpy/tree/master/doc).

***

**Troubleshoot:**

**Mouse and keyboard do not work**

On some devices, you may need to enable an option to allow simulating input. In developer options, enable:

**USB debugging (Security settings)**\
**Allow granting permissions and simulating input via USB debugging**

Rebooting the device is necessary once this option is set.