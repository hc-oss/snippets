---
tags: [NFS, shared, volume]
icon: ":card_file_box:"
---

# Shared Mount Using NFS

### On the Host (10.0.0.1)

```sh
sudo apt update
sudo apt install nfs-kernel-server

sudo mkdir -p /app/data

sudo nano /etc/exports
# /app/data    10.0.0.2(rw,sync,no_subtree_check)

sudo systemctl restart nfs-kernel-server
```

### On the Client (10.0.0.2)

```sh
sudo apt update
sudo apt install nfs-common

sudo mkdir -p /app/data

# immediately mount volume
sudo mount 10.0.0.1:/app/data /app/data

sudo nano /etc/fstab
# 10.0.0.1:/app/data   /app/data   nfs     auto    0       0

# verify mount
df -h
```
