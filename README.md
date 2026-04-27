# arm-topo

---
### Github
https://github.com/arm/topo

---
### Install topo - Linux and macOS

```
curl -fsSL https://raw.githubusercontent.com/arm/topo/refs/heads/main/scripts/install.sh | sh
```

---
### Getting Started

```
topo setup-keys --target ssh://demo@192.168.52.56
topo health --target demo@192.168.52.56
```


```
demo@cx8:~/labs/topo$ topo health --target demo@192.168.52.56
Host
----
Topo: ✅ (topo)
SSH: ✅ (ssh)
Container Engine: ✅ (docker)

Target
------
Connectivity: ✅
Container Engine: ❌ (ssh command to ssh://demo@192.168.52.56 failed: exit status 1 | stderr: errors pretty printing info
)
  → Ensure current user can run docker commands
Hardware Info: ✅ (lscpu)
Subsystem Driver (remoteproc): ℹ (no remoteproc devices found)
```
