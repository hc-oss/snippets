---
tags: [linux, service, error, log]
icon: ":warning:"
---

# Linux service error log

It often happens that linux serivce fails to start and there's no error message except failed to start below is the command that allows user to view log of service

```bash
sudo journalctl -u <service>
```
