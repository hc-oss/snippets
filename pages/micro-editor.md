---
tags: [micro, editor, vim, nano]
icon: ":technologist:"
---

# Setting up Micro

[Micro](https://micro-editor.github.io/) a modern and intuitive terminal-based text editor alternative to Vim

```bash
sudo apt-get install xclip # optional for clipboard support
curl https://getmic.ro | bash
mv micro /usr/bin # optional to use micro from anywhere
```

!!!
If using over ssh then use `-X` flag for x11 forwarding and install `xclip` on both client and server
!!!

update `.config/micro/settings.json` to avoid paste glitches

```
{
    "autoindent": false,
    "tabsize": 2,
    "tabstospaces": true
}
```
