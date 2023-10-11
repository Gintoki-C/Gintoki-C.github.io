---
title: git问题汇总
date: 2023-10-10 17:04:23
tags: git
---
### warning Permanently added ‘github.com’ (ED25519) to the list of known hosts. git@github.com
**原因** git SSH密钥不对
1. 检查本地是否有密钥
`ls ~/.ssh` 大概率出现 `known hosts`
2. 生成新密钥
`ssh-keygen -t ed25519 -C "xxx@xxx.com"`
> 邮箱名可随便填写；一直回车
3. 检查生成的密钥
`ls ~/.ssh`
4. 复制公钥并在git上配置
`cat ~/.ssh/id_ed25519.pub`
> 个人设置settings --> SSH and GPG keys -->new SSH keys
> 复制粘贴刚刚获得的公钥
