---
description: Tested on Fedora 43 Workstation
icon: fedora
---

# Install Cloudflare WARP on Fedora

#### Add Cloudflare Repository

```bash
sudo dnf config-manager addrepo --from-repofile=https://pkg.cloudflareclient.com/cloudflare-warp-ascii.repo
```

#### Install Cloudflare WARP

```bash
sudo dnf install cloudflare-warp
```

#### Check CLI Commands

```shellscript
warp-cli --help
```

#### Register Device

```shellscript
warp-cli registration new
warp-cli registration show
```

#### Connect WARP

```shellscript
warp-cli connect
```

#### Check Status

```shellscript
warp-cli status
```

#### Disconnect WARP

```shellscript
warp-cli disconnect
```
