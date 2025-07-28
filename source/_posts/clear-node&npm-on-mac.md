---
title: mac上彻底清除node和npm
date: 2018-08-28 19:12:09
tags:
  - mac
  - clear node
  - clear-npm
---
执行一下指令即可：
```bash
sudo rm -rf /usr/local/{bin/{node,npm},lib/node_modules/npm,lib/node,share/man/*/node.*}
```