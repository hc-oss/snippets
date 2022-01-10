---
tags: [port]
icon: ":hocho:"
---

# Kill Port

```text
kill -9 $(lsof -t -i:8080 -sTCP:LISTEN)
```

## Simple Way

```bash
npx kill-port 8080
```