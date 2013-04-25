---
layout: post
title: "zsh中使用ssh时tab自动补全只读取known_hosts"
description: "zsh中使用ssh时tab自动补全只读取known_hosts，不再读取.ssh/config和/etc/hosts"
category: zsh
tags: [zsh,ssh]
---

在zsh中使用ssh的自动补全功能时，如果你的`/etc/hosts`文件里指了一堆host，用tab补全会将hosts中的域名全部遍历出来，而这些host实际上根本不是我们想ssh到的地方，真正我们需要补全的往往是我们之前ssh过的，`known_hosts`中的host。

### 解决方案

 在`~/.zshrc`中，加入
 
     zstyle -e ':completion::*:*:*:hosts' hosts 'reply=(${=${${(f)"$(cat {/etc/ssh_,~/.ssh/known_}hosts(|2)(N) /dev/null)"}%%[# ]*}//,/ })'
