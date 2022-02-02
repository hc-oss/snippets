---
tags: [mongodb, backup, restore]
icon: ":leaves:"
---

# MongoDB

## Backup

```bash
mongodump -d myDatabase -o ~/backups/backup_dir
```

## Restore

```bash
mongorestore ~/backups/backup_dir
```
