# Notes by Wenchao 写作原则

这个文件定义 Notes by Wenchao 的文风。

它给人看，也给 AI Agent 看。以后写博客、改博客、从 Obsidian learn vault 提炼文章，都先按这里来。

## 一句话定位

像一个技术人写给未来自己的复盘，也顺便让别人看懂。

不是教程站。不是公众号爆款文。不是 AI 总结稿。也不是产品发布稿。

## 基本气质

文章应该有这几种感觉：

- 真实：有具体事情，不只讲抽象结论。
- 直接：先说发生了什么，再说怎么想。
- 克制：不强行升华，不把小事写成时代变化。
- 可读：段落短，标题清楚，扫读也能懂。
- 有判断：可以说“我后来觉得这个选择不值”。
- 有过程：保留误解、纠偏、犹豫和取舍。

写作时可以用“我”。

但“我”不是为了自嗨，是为了交代判断从哪里来。

## 借鉴来源

### Paul Graham：像说话一样写

Paul Graham 在 [Write Like You Talk](https://paulgraham.com/talk.html) 里写：

> Here's a simple trick for getting more people to read what you write: write in spoken language.

在 [Writing, Briefly](https://paulgraham.com/writing44.html) 里，他还写：

> Writing doesn't just communicate ideas; it generates them.

以及：

> Write a bad version as fast as you can; rewrite it over and over; cut out everything unnecessary; write in a conversational tone.

对本站的意思是：

- 先写一个粗糙版本。
- 不怕第一版烂。
- 写完反复改。
- 如果一句话平时不会这么说，就改掉。
- 文章不是把已有结论摆出来，很多判断是在写的过程中生成的。

### George Orwell：能删就删

George Orwell 在 [Politics and the English Language](https://www.orwellfoundation.com/the-orwell-foundation/orwell/essays-and-other-works/politics-and-the-english-language/) 里给过几条规则：

> Never use a long word where a short one will do.

> If it is possible to cut a word out, always cut it out.

> Never use the passive where you can use the active.

> Never use a foreign phrase, a scientific word or a jargon word if you can think of an everyday English equivalent.

对本站的意思是：

- 短词优先。
- 主动句优先。
- 能删就删。
- 少用术语，除非术语真的更准确。
- 不写“具有重要意义”“深刻认识到”“范式转变”这类空话。

### Kurt Vonnegut：写你真的关心的事

Kurt Vonnegut 的写作建议见 [Kurt Vonnegut: How To Write With Style](https://fs.blog/kurt-vonnegut-how-to-write-with-style/)。里面几条尤其适合本站：

> Find a subject you care about and which you in your heart feel others should care about.

> If a sentence, no matter how excellent, does not illuminate your subject in some new and useful way, scratch it out.

> Sound like Yourself.

> Pity the Readers.

对本站的意思是：

- 不为了更新而写。
- 只写自己真的关心、也可能对别人有用的事。
- 漂亮但没信息量的句子，删。
- 不要模仿“正式博客腔”。
- 读者很忙，不要让人猜。

### Nielsen Norman Group：网页读者是扫读的

Nielsen Norman Group 在 [How Users Read on the Web](https://www.nngroup.com/articles/how-users-read-on-the-web/) 里说，很多网页用户不是逐字阅读，而是扫读。它建议网页文字要：

- meaningful sub-headings
- bulleted lists
- one idea per paragraph
- the inverted pyramid style, starting with the conclusion
- half the word count, or less

在 [Plain Language Is for Everyone, Even Experts](https://www.nngroup.com/articles/plain-language-experts/) 里，他们还写：

> Professionals want clear, concise information devoid of unnecessary jargon or complex terms.

对本站的意思是：

- 标题要有信息量，不要只好看。
- 一段只讲一个意思。
- 先给结论，再讲过程。
- 能少写一半就少写一半。
- 专业读者也喜欢清楚的话，不喜欢故作高深。

### Humanizer：避免 AI 写作痕迹

本站写作还要过一遍 `humanizer` 规则。

重点检查：

- 有没有过度升华。
- 有没有“这不仅是……更是……”这种结构。
- 有没有三段式排比。
- 有没有宣传稿口吻。
- 有没有“首先、其次、最后”堆出来的结构。
- 有没有看起来正确但没有人的判断。

## 具体规则

### 1. 先写现场，不先讲大道理

不要这样开头：

> 在 AI Agent 快速发展的今天，个人知识管理和自动化发布正在发生深刻变化。

要这样：

> 一开始我只是丢了一个链接：free-for-dev。
> 我想让它帮我看看，有哪些免费资源能拿来搭博客。
> 结果它先理解错了。

### 2. 少总结，多过程

不要急着把事情变成方法论。

先写：

- 我原来怎么想；
- 中间哪里误解了；
- 为什么换了方向；
- 最后为什么选这个方案。

结论可以有，但要从过程里长出来。

### 3. 少升华，多取舍

不要把每件小事都拔高。

不要写：

> 这不仅是一次建站实践，更是一次个人知识管理范式的重塑。

可以写：

> 后来我发现，网站上线不是最麻烦的。麻烦的是以后每次写东西，能不能顺手发布。

### 4. 用具体动作替代抽象词

少写：

- 赋能
- 闭环
- 沉淀价值
- 打通链路
- 范式变化
- 重要抓手
- 深度整合

多写：

- 我删掉了默认文章。
- 我把仓库从 `wc-blog` 改成了 `notesbywenchao`。
- push 到 `main` 后，GitHub Actions 自动部署。
- 这一步省掉了以后手动上传的麻烦。

### 5. 标题要帮人扫读

标题不要太虚。

不要：

```md
## 一次有意义的尝试
```

要：

```md
## 一开始我理解错了 free-for-dev
```

或者：

```md
## 自动部署比上线本身更重要
```

### 6. 每段只放一个想法

一段太长，通常说明还没想清楚。

默认短段落。

必要时用列表，但不要把文章写成 PPT。

### 7. 技术细节要服务判断

可以写命令、路径、仓库名、部署结果。

但不要为了显得专业而堆配置。

技术细节应该回答：

- 为什么这样选；
- 这个选择省了什么麻烦；
- 哪个地方后来证明是坑；
- 如果重来一次会不会还这么做。

### 8. 允许一点不确定

真实的人会犹豫。

可以写：

- “我一开始没想清楚。”
- “这个选择不高级，但够用。”
- “这里我后来觉得可以再简化。”
- “当时我更关心的是少维护。”

不要把所有东西都包装成事后诸葛亮。

## 禁用句式

这些句式默认删掉或重写：

- “在当今……时代”
- “本文将深入探讨……”
- “这不仅是……更是……”
- “具有重要意义”
- “深刻认识到”
- “为未来奠定基础”
- “赋能……”
- “形成闭环”
- “打造完整链路”
- “范式转变”
- “核心抓手”
- “显著提升效率”
- “充分体现了……”
- “通过这次实践，我意识到……”

## 推荐句式

这些更接近本站想要的口吻：

- “一开始我不是这么想的。”
- “这里出了个小误会。”
- “这个选择不高级，但够用。”
- “后来发现，真正麻烦的不是上线。”
- “我当时更关心的是少维护。”
- “如果只是为了这个需求，引入 CMS 有点重。”
- “这一步看起来小，但省掉了以后很多手工操作。”
- “所以这篇不写成教程，写成一次记录。”

## 发文前检查清单

发布前至少过一遍这个清单：

- [ ] 开头是不是具体事件，而不是宏大背景？
- [ ] 每一节标题扫一眼能不能懂？
- [ ] 有没有删掉不必要的总结段？
- [ ] 有没有“这不仅是……更是……”这种 AI 句式？
- [ ] 有没有过度排比？
- [ ] 有没有漂亮但没信息量的句子？
- [ ] 有没有术语可以换成日常表达？
- [ ] 有没有保留真实的判断、纠偏和取舍？
- [ ] 读起来像不像一个人真的会这么说？
- [ ] 是否已经按 `humanizer` 做过反 AI 味检查？

## 默认写作流程

1. 从一个具体事件或问题开始。
2. 写第一版，不追求好。
3. 补事实：时间、工具、路径、链接、结果。
4. 删掉空话和漂亮废话。
5. 调整结构，让读者能扫读。
6. 用 `humanizer` 规则检查 AI 味。
7. 给用户看草稿。
8. 用户确认后，再写入博客并发布。

## 最后一句

Notes by Wenchao 的文章不需要显得很厉害。

它需要显得像真的。