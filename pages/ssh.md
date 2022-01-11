---
tags: [ssh, local-tunnel, port-forward]
icon: ":computer:"
---

# SSH

<!--email_off-->

## Local Port Forward/Tunnel

```bash
ssh -L 5432:127.0.0.1:5432 user@server
```

## Forward X

Ever wanted to access graphical application from remote ssh machine and instead of configuring VNC you can directly use -X flag with ssh and done!

```bash
ssh -X user@server
```

<!--/email_off-->