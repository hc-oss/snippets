---
tags: [copy, remote, linux, scp]
icon: ":page_facing_up:"
---

# SCP (secure copy protocol)

<!--email_off-->

```bash
# From client to server
scp localfile.zip remoteuser@server:/home/remoteuser

# From server to client
scp remoteuser@server:/home/remoteuser/remotefile.zip /home/localuser
```

<!--/email_off-->

!!!
Use `-r` Recursively copy entire directories
!!!
