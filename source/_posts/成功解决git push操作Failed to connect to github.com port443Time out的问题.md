---
title: 成功解决git push操作Failed to connect to github.com port443Time out的问题
date: 2024-07-30 14:40:57
tags: Git
---

最近在使用Git的时候push操作一直报

```
fatal: unable to access 'https://github.com/EvansLeeSin/EvansLeeSin.github.io.git/': Failed to connect to github.com port 443 after 21061 ms: Couldn't connect to server
或者是
fatal: unable to access 'https://github.com/EvansLeeSin/EvansLeeSin.github.io.git/': Failure when receiving data from the peer
```

当时认为GitHub间歇性连接不上情有可原，我也没挂梯，想着过会再push试下，发现提了好几次都这样，这就感觉不对劲了

尝试修复了Host无果，搜了下网上都是

`git config --global --unset http.proxy`
`git config --global --unset https.proxy`

统一的取消代理，试了不行

玄学操作就好使了

```
设置代理
$ git config --global https.proxy

取消代理
$ git config --global --unset https.proxy

再次提交
$ git push -u origin master
```

个人理解为默认是没有代理的(我之前的好使也没设置过代理)，所以取消代理的操作是无效的，只有设置代理->取消代理的操作相当于重置了代理网络。
