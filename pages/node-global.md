---
tags: [node, global, sudo, permission]
icon: ":wrench:"
---

# Node.js global package permission issue

Mostly nowadays everyone uses [NVM](https://github.com/nvm-sh/nvm) to setup Node.js which is easy and recommended
but sometimes like in CI Systems you need to use global instance but still don't want to mess with permissions below is simplest way

```
mkdir ~/npm-global
npm config set prefix '~/npm-global'
sudo echo "export PATH=~/npm-global/bin:$PATH" >> ~/.profile
```

after this logout and login again to see the effects now global modules installes without any error
