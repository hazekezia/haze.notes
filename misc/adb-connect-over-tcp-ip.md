---
icon: android
description: This notes for connect android using ADB using wireless connection
---

# ADB: Connect over TCP/IP

On your Android device (assuming you have already enabled developer options)

1. Go to Settings
2. Select System
3. Select Developer Options
4. Enable USB Debugging and Wireless Debugging
5. Select Wireless Debugging
6. Select Pair device using a pairing code
7. Note the IP address and the port

On your computer (assuming you have installed adb and have it on the path)

Go to your command line app, run&#x20;

```
adb pair ip:port pairing-code
```

Then

```
adb connect ip:port
```

***
