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

This script is using for auto connect, make sure your ADB is already connected to your PC using pair code.

```bash
adb pair ip:port pairing-code
```

Notes: This is modification code from `scrcpy-noconsole.vbs`

```sh
CreateObject("Wscript.Shell").Run "adb connect ip:port", 0, true

strCommand = "cmd /c scrcpy.exe"

For Each Arg In WScript.Arguments
    strCommand = strCommand & " """ & replace(Arg, """", """""""""") & """"
Next

CreateObject("Wscript.Shell").Run strCommand, 0, false
```

IP and port sometimes changes if you reconnect wireless connection. Make sure to change this everytime it changes.

***

**Troubleshoot:**

**Mouse and keyboard do not work**

On some devices, you may need to enable an option to allow simulating input. In developer options, enable:

**USB debugging (Security settings)**\
**Allow granting permissions and simulating input via USB debugging**

Rebooting the device is necessary once this option is set.

***

**Useful daily commands**

Running APKs on virtual display:

{% code overflow="wrap" fullWidth="false" %}
```
scrcpy --new-display=1920x1080 --start-app=<package_apk_name>

// Example running Genshin Impact on virtual display
scrcpy --new-display=1920x1080 --start-app=com.miHoYo.GenshinImpact
```
{% endcode %}

Running input only (no audio and video)

```
scrcpy --no-video --no-audio -M
```
