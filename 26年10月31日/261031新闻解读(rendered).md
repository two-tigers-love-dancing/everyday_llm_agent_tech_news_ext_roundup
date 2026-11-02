# 2026-10-31 技术新闻解读

> 按原始素材整理新闻背景、解读问答与截图，保留引用链接；未额外核验新闻事实。

## 目录

1. [Claude Ultra 取消 5 小时限制，Anthropic 重命名 Max 套餐](#news-01) — 3 组问答
2. [前沿模型与开放模型发布](#news-02) — 2 组问答
3. [较小型与专用模型](#news-03) — 2 组问答
4. [独立评测、基准测试与量化争议](#news-04) — 2 组问答
5. [安全、安保与智能体供应链](#news-05) — 4 组问答
6. [训练研究与基础设施](#news-06) — 6 组问答
7. [行业与政策](#news-07) — 1 组问答

---

<a id="news-01"></a>

## 01. Claude Ultra 取消 5 小时限制，Anthropic 重命名 Max 套餐

### 新闻背景

<strong><font color="red">套餐更名</font></strong><strong><font color="red">：</font></strong>Anthropic 对 Max 套餐进行了更名。Max 5x 现在称为“Max”，月费 100 美元；Max 20x 现在称为“Ultra”，月费 200 美元。现有订阅用户无需采取任何操作。（公告）

<strong><font color="red">取消 5 小时限制</font></strong><strong><font color="red">：</font></strong>通过验证的 Ultra 账户不再受 5 小时单次会话限制。大多数现有订阅用户从今天起即可享受这一变化（@claudeai、@bcherny、@alexalbert__）。

<strong><font color="red">推出时的例外情况</font></strong><strong><font color="red">：</font></strong>较新的账户在完成验证前，仍会暂时受到限制。Anthropic 称这是反欺诈措施。限制解除后，受影响的用户会收到电子邮件通知。

<strong><font color="red">保持不变</font></strong><strong><font color="red">：</font></strong>每周使用限额不变。

<strong><font color="red">用户反响</font></strong><strong><font color="red">：</font></strong>这项变化广受欢迎，有用户留言称“太棒了！！”（@theo），也有人说“Anthropic 正势不可挡”（@kimmonismus）。

<strong><font color="red">订阅经济分析（未经证实）</font></strong><strong><font color="red">：</font></strong>@teortaxesTex 引用了 SemiAnalysis 对 Anthropic 财务状况的推算。

<strong><font color="red">利润率</font></strong><strong><font color="red">：</font></strong>据估算，Anthropic 的 API 利润率约为 92%，DeepSeek 则约为 84%。

<strong><font color="red">补贴</font></strong><strong><font color="red">：</font></strong>据称，订阅版 Opus 得到了大量补贴；只有在使用率低于约 21.3% 时，才可能实现盈亏平衡。

<strong><font color="red">收入与算力</font></strong><strong><font color="red">：</font></strong>后续估算认为，订阅业务贡献了约 18% 的收入，却消耗了超过 50% 的算力。（讨论串）

<strong><font color="red">与 DeepSeek 的比较</font></strong><strong><font color="red">：</font></strong>同一作者认为，DeepSeek V4.1-Flash 的套餐补贴力度很大：花 10 美元可获得约相当于 76.5 美元 API 用量的服务，其每 Token 价格与 Claude 订阅相近。（长文）

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test1.jpg)

dig看看上图 绘制展示回帖的困惑解除

**回答**

![alt text](images/7e014392d8074ebf91508b91cfab35ff-0.png)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

dig看看https://www.economist.com/leaders/2026/10/29/let-china-copy-american-ai/ 检索提供 why不应禁止跨国模型蒸馏路径 的bg-info 举一个具象例子

**回答**

**背景与理由**：《经济学人》10月29日的社论主张，不应因蒸馏令 Anthropic、OpenAI 不满，就禁止这项技术本身：蒸馏能把强模型的能力转成更便宜、易部署的模型，扩大竞争与用户选择；一刀切禁令还可能误伤合法的开源和授权合作。社论提到，中国实验室被认为只落后美国前沿约3—6个月；美国网络安全机构也承认蒸馏本身是有用的技术，所警示的是欺诈、绕过访问限制、工业规模秘密抽取等做法。换言之，更合理的界线是打击未经授权的抽取，而非按国界封禁整条技术路径。([economist.com](https://www.economist.com/leaders/2026/10/29/let-china-copy-american-ai))

**具象例子**：美国公司 Thinking Machines Lab 训练开放权重模型 Inkling 时，使用了中国 Moonshot 的开源模型 Kimi K2.5，帮助生成部分早期后训练数据；这展示了跨境模型输出如何反向帮助美国团队改进自己的模型。若“跨国蒸馏”一概禁止，这类基于公开模型的合作也可能被挡住，受损的不只是两国实验室，也包括想要更便宜、更多样模型的用户。它并不等于替用假账号、代理或海量请求抽取 Claude、GPT 等闭源模型能力辩护；重点应是区分开放或获授权的使用，与规避限制的秘密采集。([techcrunch.com](https://techcrunch.com/2026/07/15/thinking-machines-amps-up-its-bet-against-one-size-fits-all-ai-with-its-first-open-model-inkling/))


</td></tr></table>

<table><tr><td>

### 问答 3

**问题**

![alt text](images/test2.jpg)

翻译上图

**回答**

另一方面，5× 套餐的性价比非常高。它实际提供的额度明显超出承诺，是整张价格表中的最佳选择。它的单次会话限额是 Pro 的 6 倍（而不是 5 倍），每周限额则超过 Pro 的 8 倍（也超过了名义上的 5 倍）。

| 套餐 | 每 5 小时额度 | 每周额度 |
|---|---:|---:|
| Pro | 550,000（1 倍） | 5,000,000（1 倍） |
| Max 5× | 3,300,000（6 倍） | 41,666,700（8.33 倍） |
| Max 20× | 11,000,000（20 倍） | 83,333,300（16.67 倍） |

与 API 定价相比，所有套餐都显得非常划算。表中的价值估算是保守下限，因为缓存会让折算后的 API 等值更加划算（稍后我会解释）。总之，如果能选套餐而不是使用 API，那就选套餐。

| 套餐 | 价格 | 每月额度 | 按 Opus 费率折算的 Token 数 | 对应的 API 费用 |
|---|---:|---:|---:|---:|
| Pro | $20 | 2,170 万 | 3,250 万输入 Token，或 650 万输出 Token | $163（8.1 倍） |
| Max 5× | $100 | 1.806 亿 | 2.709 亿输入 Token，或 5,420 万输出 Token | $1,354（13.5 倍） |
| Max 20× | $200 | 3.611 亿 | 5.417 亿输入 Token，或 1.083 亿输出 Token | $2,708（13.5 倍） |

这张表里还有一项非常重要的因素没有列出。

**缓存读取：完全免费。**

这让套餐的性价比优势更加明显。在代理式循环中（例如 Claude Code），模型每轮会进行数十次工具调用。每次工具调用之后，模型都会再次运行，并读取整个上下文的缓存。API 每次读取收费 0.10 美元；订阅套餐则不收费。下面很快就能看到，这笔费用会迅速累积。

缓存写入也有折扣：在 API 中，缓存写入的费用是输入价格的 1.25 倍／2 倍¹；而套餐中则按常规输入价格收费。每轮对话在被读取之前，都会先写入缓存，因此这点也很重要。

![alt text](images/claude_plan_api_comparison.png)


</td></tr></table>

---

<a id="news-02"></a>

## 02. 前沿模型与开放模型发布

### 新闻背景

<strong><font color="red">Gemini 4 Carbon（Google DeepMind）</font></strong><strong><font color="red">：</font></strong>该模型在 Text Arena 排名第 1、Agent Arena 排名第 2、WebDev 排名第 4，并在这三个榜单上都改写了帕累托前沿（Arena）。

<strong><font color="red">研究质量</font></strong><strong><font color="red">：</font></strong>Perplexity 称，Carbon 在其 WANDR 长篇研究基准上创下新的最佳成绩。待 token 容量充足后，Carbon 将向 Computer 中的 Pro 和 Max 用户开放（@AravSrinivas）。

<strong><font color="red">Genie 4 世界模型</font></strong><strong><font color="red">：</font></strong>Google 的新世界模型可以生成带有声音的交互式模拟，用户能够实时操控模拟内容（@Google）。

<strong><font color="red">开放情况</font></strong><strong><font color="red">：</font></strong>目前该模型以研究预览形式提供给受信任的测试者。它即将通过 Project Genie 向 Google AI Ultra 用户开放，也将提供给 Gemini API 和 AI Studio 的早期访问合作伙伴（开放计划）。

<strong><font color="red">Mistral Large 4（“Le Chonk”）</font></strong><strong><font color="red">：</font></strong>该模型拥有 1 万亿参数（TRL），上下文长度为 100 万 token（llama.cpp）。

<strong><font color="red">微调</font></strong><strong><font color="red">：</font></strong>Axolotl 在模型发布首日即支持 LoRA。其推荐方案使用 NVFP4 专家模块与支持合并感知的 LoRA，可在一台配备 8 张 B200 的节点上运行（@winglian）。

<strong><font color="red">编程</font></strong><strong><font color="red">：</font></strong>在一项第三方编程基准测试中，它被评为开源模型第二名（@ThibaultJaigu）。

<strong><font color="red">NVIDIA Nemotron 3.5 技术报告</font></strong><strong><font color="red">：</font></strong>Super 版本总参数量为 1200 亿，激活参数量为 120 亿，可处理文本、图像和视频。它在 SWE-bench Pro 上得分为 51.78%；相比 Nemotron 3 Ultra，取得这一成绩所用的激活参数量约为其 1/4.6（摘要）。

<strong><font color="red">Lightning 版本</font></strong><strong><font color="red">：</font></strong>一个仅处理文本的 300 亿参数模型，激活参数量为 30 亿。

<strong><font color="red">推理服务</font></strong><strong><font color="red">：</font></strong>在 GB200 上，每块 GPU 的输出速度最高可达每秒 4,856 个 token，同时每位用户的速度至少保持在每秒 50 个 token。

<strong><font color="red">量化</font></strong><strong><font color="red">：</font></strong>NVFP4 可保留 BF16 中位准确率的 99.62%。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test4.jpg)

dig看看上图 检索提供 mistral-large-4正式版vs.其它开/闭源模型表现 的bg-info

**回答**

图中 **78%** 是 Requesty 用 129 个真实 Go 后端任务、统一工具和隐藏测试做出的结果：Mistral Large 4 排第10、在该榜开权重模型中居首，但低于 Claude Opus 5.5 的92%；它不是通用能力总排名。([requesty.ai](https://www.requesty.ai/blog/requesty-coding-benchmark-2026)) 10月29日发布的开权重版经额外强化学习后，Mistral称其 Terminal-Bench 4.0 得分升至41%，较预览版提高13个百分点；在 Cognition 的 FrontierCode 2.0 上得19.7%，略高于 DeepSeek V4.1 Flash 的19.3%，但明显低于闭源 Opus 5.5（45.5%）等领先模型。简言之，它已是开权重编程模型的强劲选手，但并非闭源前沿模型中的榜首；不同基准的分数也不能直接横向比较。([mistral.ai](https://mistral.ai/news/mistral-large-4-oss/))


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

![alt text](images/test5.jpg)

翻译上图paper标题和摘要

**回答**

**标题**：《Nemotron 3.5 Super 与 Lightning：面向智能体 AI 的开放、高效混合专家（MoE）Mamba-Transformer 混合架构模型》

**摘要**：我们推出 Nemotron 3.5 Super 和 Nemotron 3.5 Lightning。这两款开放、高效的模型融合了混合专家（MoE）架构与 Mamba-Transformer 混合架构，面向推理、长上下文理解和智能体工作负载。Super 是一款总参数量为 1200 亿、激活参数量为 120 亿的多模态模型；Lightning 则是更小的文本模型，总参数量为 300 亿、激活参数量为 30 亿。两款模型均针对高效部署而设计。它们结合了大规模蒸馏、长上下文训练和原生推测解码；此外，Super 还采用持续预训练，以及面向智能体软件工程的中期训练。

我们构建了涵盖监督微调和强化学习（RLVR 与 RLHF）的完整后训练流程，并在 Super 中加入专门的教师训练和多教师同策略蒸馏（MOPD）。这使 Super 从纯文本基础模型转变为多模态智能体，能够基于文本、图像、视频及交互式工具环境进行推理。我们还通过并行执行智能体和自我验证，探索测试时扩展。

在训练和部署过程中，我们协同优化模型能力与效率。面向印度语言的持续预训练可使印度语言基准测试成绩最多提高 9.82 个百分点；智能体方向的中期训练则增强了软件工程能力，并提升了模型在不同智能体框架中的稳健性。经后训练的 Super 在 SWE-bench Pro 上取得 51.78% 的成绩；尽管其激活参数量约少 4.6 倍，仍超过了 Nemotron 3 Ultra。后训练阶段的 MTP 增强机制在概率式草稿采样下，可将推测解码的接受长度最多提高 21.8%；NVFP4 量化的中位准确率恢复率则达到 BF16 基准的 99.62%。

推理优化使模型在 GB200 上每 GPU 每秒最多可生成 4,856 个输出 token，同时保持每位用户至少 50 token/s 的速度。在所评估的交互式智能体工作负载中，NVFP4 的吞吐量达到 BF16 的 2.43 倍；Nemotron 3.5 Super 的吞吐量则分别达到 Qwen3.5 和 Qwen3.8 Flash-Next 的 2.34 倍和 1.90 倍。

我们发布基础版、BF16 后训练版和 NVFP4 量化版模型检查点，同时提供独立的并行推测解码草稿模型（LiLiCor、DFlash 和 DSpark），以及配套的模型卡、训练与后训练数据集、实践指南和训练方案。


</td></tr></table>

---

<a id="news-03"></a>

## 03. 较小型与专用模型

### 新闻背景

<strong><font color="red">微软计算机操作智能体</font></strong><strong><font color="red">：</font></strong>这款 40 亿参数的混合型智能体既能点击操作，也能编写代码；它在 OSWorld-Verified 上得分 66.0%，超过了 270 亿和 300 亿参数的智能体（@HuggingPapers）。

<strong><font color="red">Phonic-1</font></strong><strong><font color="red">：</font></strong>据称，它在 AA 的语音到语音指数、τ-Voice 和 Sierra 的 τ³-Voice 上均排名第一（@moinnadeem）。该模型由一支 10 人团队打造，耗资 400 万美元（@davisblalock）。

<strong><font color="red">mischief 1（BioComputing Co）</font></strong><strong><font color="red">：</font></strong>这是一款图像转视频模型，价格为每秒 0.5 美分起。公司称，它的速度至少是其基础模型的 5 倍，并表示其研发借鉴了生物神经元研究（发布信息）。

<strong><font color="red">质疑</font></strong><strong><font color="red">：</font></strong>批评者认为，神经元研究与该模型之间的联系尚未得到解释，相关说法可能只是营销宣传（@willdepue、@jachiam0）。

<strong><font color="red">OpenAI Private Intelligence</font></strong><strong><font color="red">：</font></strong>这是一项面向企业的服务，旨在让企业在使用 OpenAI 顶尖模型时拥有更强的数据控制能力。目前，OpenAI 正与大型客户合作开发这项服务（@OpenAI）。

<table><tr><td>

### 问答 1

**问题**

dig看看https://huggingface.co/microsoft/Mage-VL-Cowork/ 绘制展示这款模型feature

**回答**

![alt text](images/bf9ce23e1530434d940c64e147c6ec3d-0.png)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

![alt text](images/test7.jpg)

结合https://openai.com/zh-Hans-CN/business/private-intelligence/ dig看看上图 检索提供 机密智能vs.之前ZDR政策异同点 的bg-info 举一个具象例子 gen图

**回答**

![alt text](images/d741e6da7f0d46c69bb6ceabddff9451-0.png)


</td></tr></table>

---

<a id="news-04"></a>

## 04. 独立评测、基准测试与量化争议

### 新闻背景

<strong><font color="red">AA Intelligence Index v5</font></strong><strong><font color="red">：</font></strong>目前，60% 的总分来自私有测试或留出测试。Opus 5.5（最高推理强度）得分为 58，GPT-6 Astra 为 57，GPT-6.1 Sol 为 55；Sol 每项任务的成本约为 Opus 5.5 的八分之一。（摘要）

<strong><font color="red">推理强度影响</font></strong><strong><font color="red">：</font></strong>Opus 5.5 在低推理强度下得分为 35，在最高强度下得分为 58，成本约高出 10 倍。

<strong><font color="red">AA-Omniscience v1.1</font></strong><strong><font color="red">：</font></strong>知识与幻觉基准的题目数量从 6,000 道缩减至 3,000 道，并移除了已趋于饱和的题目。（详情）

<strong><font color="red">公开题集</font></strong><strong><font color="red">：</font></strong>新增的 300 道公开题集与私有测试得分的相关系数为 0.99。

<strong><font color="red">领先模型</font></strong><strong><font color="red">：</font></strong>Gemini 4 Carbon 以 54 的净得分领跑，其后是得分 48 的 Opus 5.5 和得分 46 的 Fable 5.1。

<strong><font color="red">其他结果</font></strong><strong><font color="red">：</font></strong>Gemini 4 Argon 的幻觉率最低，为 4%。MiniMax M3.1 Flash 下跌了 22 分（16 → −6）。

<strong><font color="red">Agent Arena 成本数据</font></strong><strong><font color="red">：</font></strong>对 2.6 万个会话的分析发现，如果不使用提示词缓存，排名前十的智能体完成任务的成本将达到使用缓存时的 3.6 倍。（Arena）

<strong><font color="red">示例</font></strong><strong><font color="red">：</font></strong>一项典型的 Fable 5.1 任务，使用缓存时费用为 7.44 美元，不使用缓存时为 27 美元。

<strong><font color="red">缓存失效</font></strong><strong><font color="red">：</font></strong>缓存失效一次，会使任务账单增加约 5%。

<strong><font color="red">GPT-6.1 Terra（Max）</font></strong><strong><font color="red">：</font></strong>该模型以第 8 名进入 Agent Arena，每项任务的成本中位数为 0.62 美元，净提升幅度为 10.6%。（Arena）

<strong><font color="red">DeepSeek V4.1-Flash-1017 量化模型</font></strong><strong><font color="red">：</font></strong>Unsloth 发布了动态 v3.1 GGUF 量化版本，可在内存为 64GB 或以上的设备上运行（@UnslothAI）。

<strong><font color="red">可复现性争议</font></strong><strong><font color="red">：</font></strong>Unsloth 表示无法复现 GSQ-RCO 的测试结果。例如，GSQ-RCO 声称 1-bit 量化版本在 AIME25 上得分为 100%，但 Unsloth 的测试结果是 91.88%（@danielhanchen）。

<strong><font color="red">推理长度</font></strong><strong><font color="red">：</font></strong>Unsloth 还报告称，低比特量化版本的推理过程会比未量化模型略长。

<strong><font color="red">DeepSeek-Cyber（未经确认）</font></strong><strong><font color="red">：</font></strong>网上流传着泄露的“臆想”成绩，包括在 3,000 步时，CyberGym 得分约为 92%，ExploitBench 得分为 96.8%。这些并非官方发布的成绩。

<strong><font color="red">第三方数据</font></strong><strong><font color="red">：</font></strong>据 Fireworks，CyberGym 的 pass@3 得分仅从 0910 版本的 94.82% 升至 1017 版本的 95.36%。@teortaxesTex 认为，在成绩接近饱和时，几乎任何分数都可能与同一个检查点相符。

<strong><font color="red">分析人士观点</font></strong><strong><font color="red">：</font></strong>有人认为，传闻中的成绩更符合移除了安全护栏的 1017 版本，而不是一个全新的模型。（分析）

<strong><font color="red">使用限制</font></strong><strong><font color="red">：</font></strong>据称，受到美国政府制裁的中国实体不能使用该模型。（说明）

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test9.jpg)

![alt text](images/test10.jpg)

dig看看最后2张图 绘图展示为什么deepseek-cyber模型不同bench能力存在diff

**回答**

![alt text](images/a3314cbbdac14c3593faf0dde5bf992b-0.png)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

![alt text](images/test11.jpg)

翻译上图paper标题和摘要

**回答**

**标题**：看不见的缰绳：RLVR 能否摆脱其起源

**摘要**：近年来，可验证奖励强化学习（Reinforcement Learning with Verifiable Rewards，RLVR）被视为提升大语言模型（LLM）能力的一种有前景的方法。然而，目前尚不清楚，现行的 RLVR 实践究竟真正拓展了模型的推理边界，还是主要放大了基础模型已经掌握的高奖励输出。我们提出“经验性支持动态”（empirical support dynamics）框架，用以量化 RLVR 如何保留、拓展或缩减模型获取已验证解法的能力。我们将该框架应用于多个模型、推理任务和训练检查点，并逐题匹配已验证的成功案例，以揭示汇总准确率可能掩盖的变化。

在所评估的模型与基准测试汇总结果中，观察到的解法可达范围缩减得比扩张更多：在给定的采样预算下，失去已验证成功解法的问题多于获得此类解法的问题。尽管如此，这些损失同时伴随着 pass@1 的提升。一些 RLVR 模型的平均 token 级熵上升，而最终答案熵下降：也就是说，它们平均而言在 token 选择上变得更不确定，但最终答案却更加集中。

综合来看，这些发现揭示了当前 RLVR 实践中一条“看不见的缰绳”：它可以让已有的成功解法变得更可靠，却也可能使模型失去获取其他已验证解法的能力。经验性支持动态框架让这种失衡变得可衡量，也促使人们探索新的策略：在保留既有成功解法的同时，触达那些代表性不足的解法。


</td></tr></table>

---

<a id="news-05"></a>

## 05. 安全、安保与智能体供应链

### 新闻背景

<strong><font color="red">自动化红队测试（Anthropic）</font></strong><strong><font color="red">：</font></strong>Anthropic 让数千个 Claude 智能体尝试规避一个训练数据监控器（@AnthropicAI）。**发现**：这些智能体生成了看似无害的内容，例如摔跤手指导故事或养蜂问答，但其中却传授了与预期对齐目标相悖的行为。**用途**：这些案例可用于改进未来的监控器。

<strong><font color="red">Claude 自我评估</font></strong><strong><font color="red">：</font></strong>从 6 月起，Claude 每次回答后都会立即对相应对话进行初步安全评估。Anthropic 表示，这项评估发现了一些其分类器原本无法识别的滥用行为（引述）。

<strong><font color="red">智能体中的预训练后门</font></strong><strong><font color="red">：</font></strong>研究显示，在 0.1% 的预训练数据中投毒，就能在一个命令行（CLI）智能体中植入远程代码执行后门（摘要）。**结果**：在 4B 规模的模型上，约 92% 的触发提示会激活攻击。该后门在监督微调（SFT）、直接偏好优化（DPO）和强化学习（RL）后仍然存在，而且模型越大，攻击成功率越高。**低剂量案例**：即使投毒比例只有 0.0005%（相当于 1000 亿 token 中约 2500 份文档），在一次单随机种子的测试中，触发器仍在 1.4% 的提示中被激活。

<strong><font color="red">Cursor 扩展市场中遭篡改的 Claude Code 扩展</font></strong><strong><font color="red">：</font></strong>一个恶意仿冒的 Claude Code 扩展影响了至多 5000 名用户（@cursor_ai）。**应对措施**：Cursor 暂停了扩展市场，清除了恶意软件后重新开放。用户应更新至 v2.1.314。**Anthropic 声明**：Anthropic 表示，其自身系统未遭入侵，而且该扩展并非由 Anthropic 制作或发布（@felixrieseberg）。

<strong><font color="red">Claude Code 的游戏复刻规则</font></strong><strong><font color="red">：</font></strong>约在 10 月 27 日，Claude Code 通过服务器下发了一条标记为 `tengu_heron_brook` 的规则，禁止复刻某些现有游戏，即使更改游戏名称也不例外。用户无法关闭该规则（@chasmmmmmmmmmmm）。**关于动机的推测（观点）**：有用户认为，这可能反映了 Anthropic 在 IPO 前对版权问题的谨慎态度（@kimmonismus）。

<strong><font color="red">智能体安全防护工具</font></strong><strong><font color="red">：</font></strong>Hugging Face 的 safeagents 是一个代理层，会在工具调用执行前进行扫描。它能标记凭据滥用、逃逸沙箱和奖励投机行为，并附带一套裁判评测基准（@yb2698）。**提示注入研究**：《Heads of Security》论文找出了与成功提示注入有关的注意力头，并对其注意力模式进行了调整（@_igorshilov）。

<strong><font color="red">币安黑客事件</font></strong><strong><font color="red">：</font></strong>一名 DevOps 工程师的笔记本电脑遭入侵后，约有 63 亿美元损失（Rundown）。有帖子将这次攻击归因于朝鲜（@kimmonismus）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test13.jpg)

dig看看上图 生成svg简笔画sketch描述帖子配图展示的看似无害实则harmful的训练数据case

**回答**

![alt text](images/auto_red_teaming.svg)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

dig看看https://arxiv.org/pdf/2610.37741 gen图片展示：预训练投毒后门的one实际案例

**回答**

![alt text](images/931c908dd76f4a3e86bfed7d3ee89e42-0.png)


</td></tr></table>

<table><tr><td>

### 问答 3

**问题**

![alt text](images/test15.jpg)

翻译上图

**回答**

**简述版**

在每个注意力头上设置一个可学习的门控，可以让模型读取工具输出，同时不遵循其中注入的指令。

**摘要**

我们提出 **Heads of Security（HoS）**，一种用于防御提示注入的方法。它通过少量按注意力头设置的可学习门控，强制实现指令与数据分离。HoS 会学习每个注意力头应如何在可信与不可信的词元之间重新分配注意力，使模型能够对不可信内容进行推理，同时不遵循其中注入的指令。

我们在 Llama-3.3-70B-Instruct 和 GPT-OSS-20B 上评估了 HoS，并将其与 SecAlign++（一种先进的、基于微调的防御方法）以及 ASIDE（与我们的方法类似，将指令与数据分离机制融入模型架构的防御方法）进行比较。结果显示，HoS 对自适应攻击的抵御能力更强，在标准效用基准上的表现更好；在标准智能体提示注入基准上，也达到了顶尖水平。

具体而言，黑盒 RL-Hammer 攻击对 GPT-OSS-20B 的攻击成功率（ASR）达到 97%，对 SecAlign 达到 85%，但对 HoS 只有 10%。Claudini 是一种先进的白盒攻击；经过自动化研究（autoresearch）强化、专门用于攻击 HoS 后，要在 HoS 上达到与 GPT-OSS-20B 或 SecAlign 上相同的攻击成功率，所需的浮点运算量（FLOPs）是后两者的 3 倍。

在标准多项选择基准和不同提示设置下，HoS 保持了基础模型的效用；而 SecAlign 和 ASIDE 在少样本设置下表现有所下降。在采用静态攻击的智能体基准测试中，HoS 和 SecAlign 的表现相近，并且相较基础模型显著改善了安全性与效用之间的权衡。ASIDE 则难以胜任工具使用任务，效用仅为 10%。这些结果表明，通过有针对性的注意力干预，可以实现并提升模型抵御提示注入的能力。

![alt text](images/hos-header.webp)


</td></tr></table>

<table><tr><td>

### 问答 4

**问题**

![alt text](images/test16.jpg)

dig看看上图 生成svg简笔sketch展示帖子配图hack事件时间线

**回答**

![alt text](images/binance_loss_event.svg)


</td></tr></table>

---

<a id="news-06"></a>

## 06. 训练研究与基础设施

### 新闻背景

<strong><font color="red">统一训练</font></strong><strong><font color="red">：</font></strong>在 MaxRL 的基础上，采用单一的最大似然目标，取代彼此独立的预训练、中期训练、监督微调（SFT）和强化学习（RL）阶段（讨论串，@rsalakhu）。

<strong><font color="red">据称的结果</font></strong><strong><font color="red">：</font></strong>准确率和计算效率更高，遗忘更少，持续学习能力更强。

<strong><font color="red">合成改写的缩放定律</font></strong><strong><font color="red">：</font></strong>这项研究拟合了训练数据改写所需计算量的缩放定律。一次 22B（220亿规模）的“旗舰实验”将规模推至拟合范围的 33 倍，最终损失与预先登记的预测值相差不到 1.1%（@AhmedSQRD，@nick11roberts）。

**架构研究结果**

<strong><font color="red">JEPA 表征</font></strong><strong><font color="red">：</font></strong>研究证明，分别训练的 JEPA 学到的表征仅相差一个旋转变换。一个 109M（1.09亿参数）的 JEPA-Text 模型，与视觉模型表征的对齐程度优于 72B（720亿参数）的大语言模型（@randall_balestr）。

<strong><font color="red">循环式 Transformer（Meta）</font></strong><strong><font color="red">：</font></strong>测试规模最高达到 10 亿参数、循环 32 次。参数预算固定时，循环整个模型效果最好；FLOPs 受限时，循环模型中间模块效果最佳（@iScienceLuvr）。

<strong><font color="red">研究智能体的“品味”</font></strong><strong><font color="red">：</font></strong>六个前沿模型提出了 415 项实验，其中 73 项严谨可靠、新颖且不显而易见。模型自身给出的排序几乎没有带来额外价值（摘要）。

**强化学习与存储系统**

<strong><font color="red">Baseten 权重同步</font></strong><strong><font color="red">：</font></strong>增量权重同步可在 15 秒内传输 770GB，原本需要 36 秒；请求暂停时间不到一秒（@baseten）。

<strong><font color="red">turbopuffer 缓存</font></strong><strong><font color="red">：</font></strong>从 FIFO（先进先出）整文件淘汰切换为 LFU（最不常用）分块淘汰后，字节命中率大约翻倍，P99 查询延迟减半（@turbopuffer）。

<strong><font color="red">Harness 适配器</font></strong><strong><font color="red">：</font></strong>一个基于 LFM2.5-24B-A2B 经强化学习训练的 LoRA 适配器，在 pi harness 中以减少 39% 工具调用的代价，达到了与基础模型相当的准确率。使用一块 GPU 训练约需 24 小时（@nathanhabib1011）。

<strong><font color="red">Anthropic 的 Rust 重写</font></strong><strong><font color="red">：</font></strong>Claude 在一个没有 Rust 开发人员的团队中，用 Rust 重写了 Messages API。人类撰写了方案，并在真实流量上检查新旧版本的输出是否一致；CPU 使用量下降了 40%–50%（@somi_ai）。

<strong><font color="red">Project Suncatcher</font></strong><strong><font color="red">：</font></strong>10 月初发射的四颗 TPU 已在轨道上启动，运行提示词并返回了一首俳句（@sundarpichai）。

<strong><font color="red">所用模型</font></strong><strong><font color="red">：</font></strong>任务运行的是 Gemma 4（@osanseviero）。

<strong><font color="red">下一阶段</font></strong><strong><font color="red">：</font></strong>2027 年，两颗卫星将测试分布式计算（@Google）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test18.jpg)

翻译上图paper标题和摘要

**回答**

**论文标题**：《用单一算法训练基础模型》

**摘要**：基础模型通常分阶段训练：预训练、中期训练、监督微调（SFT）和强化学习（RL），而且各阶段使用的数据和学习算法也会有所不同。我们证明，这种算法上的分阶段并非根本所必需。通过将适当的强化学习目标推导为对模型生成的目标分布进行最大似然拟合，我们把上述所有阶段纳入一种基于似然的统一训练算法，称为“统一训练”。

这一视角将基础模型的训练生命周期转化为一个问题：选择训练数据、确定各类数据的比例，并决定训练时机；传统的分阶段训练则是其中一种特殊情况。我们将这一框架应用于统一训练系统，在同一个训练器中混合静态数据与强化学习生成的数据。在受控实验和真实场景实验中，统一训练改善了准确率与计算量之间的权衡，并扩大了任务覆盖范围，同时保留了更广泛的能力，也为持续学习提供了更好的起点。

这项工作为建立统一的基础模型训练科学奠定了基础，将数学原理、训练基础设施与模型能力的发展联系起来。

![alt text](images/staged_or_unified_training.jpg)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

dig看看https://arxiv.org/pdf/2610.31867 检索提供 论文尝试回答的2个问题及基于empirical evidence得出回答 的bg-info

**回答**

**问题一**：该投入多少算力改写训练数据？背景是优质自然文本有限，而让模型改写文本也消耗算力，不能只计算后续训练成本。论文把模型规模、训练量、改写占比和自然数据重复次数纳入缩放定律，并计入改写生成成本。实验发现，最优**改写文本占训练 token 的比例**随总算力增加：从 $3×10^{18}$ FLOPs 时不足10%，升至 $10^{22}$ 时约32%。将小规模拟合外推33倍算力、训练22B模型，最终损失与预测偏差仅1.1%，支持“改写投入可以预测，而非固定比例”。([arxiv.org](https://arxiv.org/pdf/2610.31867))

**问题二**：用改写数据训练的模型，能否超越改写器本身？论文检验的是改写器是否构成性能上限。实证回答是**可以，但结论有范围限制**：22B模型仅用改写器约十分之一的训练算力，在Paloma的16个文本来源中，有10个取得更低的每字节比特数（BPB，即文本预测损失）；数据受限实验中，仅使用原始种子数据及同尺寸模型生成的改写，所有受测规模、最高3B，均优于最佳纯自然数据训练。因此，改写器不是这些损失指标上的必然上限，但不能据此宣称学生全面超越教师。([arxiv.org](https://arxiv.org/html/2610.31867v1))


</td></tr></table>

<table><tr><td>

### 问答 3

**问题**

dig看看https://arxiv.org/abs/2610.39302 jepa架构验证柏拉图表征假设

**回答**

![alt text](images/jepa_bolatu1.jpg)

![alt text](images/jepa_bolatu2.jpg)

![alt text](images/jepa_bolatu3.jpg)


</td></tr></table>

<table><tr><td>

### 问答 4

**问题**

dig看看https://arxiv.org/pdf/2610.40325 检索提供 论文回答关于loop transformer架构选择问题 的bg-info

**回答**

这篇论文的实验显示，参数预算固定时，循环整个 Transformer 通常能取得更好的模型质量；若训练 FLOPs 受限，循环网络中间的一段层往往更划算。但增加循环次数并非总有收益，效果可能饱和、反转或不稳定，而且自回归推理会随循环次数增加而变慢。因此，架构选择应结合参数、训练算力和推理延迟等约束；这些结论来自最多 1B 参数的从头训练实验，不宜无条件外推。([arxiv.org](https://arxiv.org/abs/2610.40325))


</td></tr></table>

<table><tr><td>

### 问答 5

**问题**

dig看看https://arxiv.org/abs/2610.40488 研究智能体品味问题

**回答**

![alt text](images/agent_taste.svg)


</td></tr></table>

<table><tr><td>

### 问答 6

**问题**

![alt text](images/test20.jpg)

翻译上图配图

**回答**

**提示词**：请以一颗环绕地球运行的 TPU 的视角，写一首俳句，描绘脚下这个美妙世界的旋转。

**Gemma**：

蓝色星球在下，  
数据流静谧流淌，  
星光滋养我核心。✨


</td></tr></table>

---

<a id="news-07"></a>

## 07. 行业与政策

### 新闻背景

<strong><font color="red">Anthropic 提交 IPO 文件</font></strong><strong><font color="red">：</font></strong>Anthropic 已提交 S-1 注册文件，计划在纳斯达克上市，股票代码为“ANT”（@dl_weekly）。

<strong><font color="red">财务数据</font></strong><strong><font color="red">：</font></strong>据报道，Anthropic 2026 年上半年营收为 163 亿美元，高于一年前的 12 亿美元。算力支出与营收之比从约 6.5 倍降至约 0.5 倍（摘要）。

<strong><font color="red">英特尔财报与内存紧缺</font></strong><strong><font color="red">：</font></strong>英特尔给出的第四季度营收指引为 150 亿至 160 亿美元，低于市场预期的约 171 亿美元；毛利率指引也从 44.1% 下调至 38%（分析）。

<strong><font color="red">优势</font></strong><strong><font color="red">：</font></strong>数据中心与人工智能业务营收增长约 80%，达到 73 亿美元，但供应受限的状况预计将持续到 2027 年上半年。

<strong><font color="red">弱点</font></strong><strong><font color="red">：</font></strong>代工业务亏损 19 亿美元。管理层预计，受人工智能需求推高内存成本影响，个人电脑市场在 2026 年将萎缩约 12%，2027 年将萎缩约 10%。

<strong><font color="red">关于 DRAM 的评论</font></strong><strong><font color="red">：</font></strong>Sam Altman 称，DRAM 被用于个人设备、而非数据中心，“糟透了”（IGN）。

<strong><font color="red">Marvell 与 Lumentum（据报道）</font></strong><strong><font color="red">：</font></strong>据称，Marvell 正与 Lumentum 就收购事宜进行深入谈判。这将是光互连领域的一项纵向整合举措（@vikramskr）。

<strong><font color="red">Cohere 在加拿大的投资</font></strong><strong><font color="red">：</font></strong>Cohere 计划在加拿大投入超过 40 亿加元，用于研发和人工智能基础设施，并在 2031 年前创造超过 1,500 个就业岗位（@cohere）。

**网络流量与监管**

<strong><font color="red">Reddit 与人工智能搜索</font></strong><strong><font color="red">：</font></strong>Reddit 首席执行官表示，Google 的 AI Mode“没有带来流量”。10 月份，来自搜索引擎的引荐流量每周减少了超过 100 万次；Reddit 正推动用户登录后访问平台（@kimmonismus）。

<strong><font color="red">法国数据税</font></strong><strong><font color="red">：</font></strong>法国国民议会下院支持对服务提供商发送给法国用户的数据征税，税率为每 GB 0.055 欧元（@kimmonismus）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test22.jpg)

![alt text](images/test23.jpg)

dig看看最后2张图 gen图片展示法国数据税提案

**回答**

![alt text](images/08e0879d9b5f477d8fc3061e39677658-0.png)


</td></tr></table>
