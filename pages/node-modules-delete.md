---
tags: [node_modules, delete]
icon: ":wastebasket:"
---

# Delete all `node_modules` folder recursively

!!!danger
This will remove every `node_modules` folder at current folder's subdirectories
!!!

```bash
find . -name "node_modules" -type d -prune -exec rm -rf '{}' +
```

!!!
You can improve performance by using `-maxdepth 2` arguement if your node_modules are only going to be N directory deep
!!!

[Reference](https://rtmccormick.com/2018/01/10/clear-node-modules-folders-recursively-mac-linux/)
