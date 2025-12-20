---
description: for all who need it
---

# Script - Restart Ethernet Adapter

Save as .bat file and run as administrator.

```bat
@echo off
netsh interface set interface "Ethernet" admin=disable
timeout /t 3 >nul
netsh interface set interface "Ethernet" admin=enable
```

Interface name can be different but usually just "Ethernet". If not sure, run `Get-NetAdapter` on PowerShell with admin privilege.
