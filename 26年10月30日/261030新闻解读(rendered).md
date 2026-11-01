# 2026-10-30 技术新闻解读

> 按原始素材整理新闻背景、解读问答与截图，保留引用链接；未额外核验新闻事实。

## 目录

1. [Mistral Large 4（“Le Chonk”）开放权重发布](#news-01) — 2 组问答
2. [架构：根据社区分析，该模型采用类似 DeepSeek V3.2 和 GLM 5 的全稀疏注意力机制。第 35 层之后的 NoPE 层共享 KV 缓存；从…](#news-02) — 5 组问答
3. [前沿监控、智能体安全与进攻性网络安全](#news-03) — 9 组问答
4. [评测、排行榜与新型专用模型](#news-04) — 3 组问答
5. [系统、基础设施与训练研究](#news-05) — 4 组问答
6. [开发者工具、产品与模型传闻](#news-06) — 2 组问答
7. [行业与政策](#news-07) — 2 组问答

---

<a id="news-01"></a>

## 01. Mistral Large 4（“Le Chonk”）开放权重发布

### 新闻背景

<strong><font color="red">发布</font></strong><strong><font color="red">：</font></strong>Mistral 为其旗舰模型发布了更新版开放权重，目标应用包括智能体编程和网络安全，并可通过 Mistral Forge 进行定制（公告、权重/博客）。

<strong><font color="red">规格</font></strong><strong><font color="red">：</font></strong>据 Artificial Analysis（AA），该模型总参数量为 1.05 万亿，激活参数量为 520 亿；支持 100 万 token 上下文及文本、图像输入。Vals 补充称，其最大输出长度为 25.6 万 token（Vals）。

<strong><font color="red">定价与许可</font></strong><strong><font color="red">：</font></strong>每 100 万输入/输出 token 分别收费 0.70 美元和 2.10 美元，缓存价格为 0.07 美元；比 Preview 版本低约 50%。MEOW 许可证规定，提供“模型即服务”（MaaS）的企业须另行取得商业许可（AA）。

<strong><font color="red">厂商说法</font></strong><strong><font color="red">：</font></strong>Mistral 称，该模型在 Cognition 的 FrontierCode 榜单中位列开放模型第一，并接受了 CrowdStrike、Cloudflare、Zscaler 等公司的网络防御测试。一位 Mistral 研究员称，该模型在人类偏好对比中对 GLM 5.3 和 Kimi K3 的胜率为 64%（@b_roziere，后续帖文）。

<strong><font color="red">独立评测</font></strong><strong><font color="red">：</font></strong>AA 在 Intelligence Index v5 中给该模型打出 26 分。它以 1 分优势超过 Muse Spark Open，成为中国以外开发的开放模型中排名最高者；不过，仍比 DeepSeek V4.1 Flash 1017 和 GLM-5.3 低 6 分（AA）。

<strong><font color="red">代码与智能体</font></strong><strong><font color="red">：</font></strong>该模型在 FrontierCode 2.0 上得分 15%，低于 DeepSeek V4.1 Flash 1017 的 29% 和 GLM-5.3 的 22%；在 Terminal-Bench 4.0 上得分 25%，高于 Muse Spark Open 的 8%。在 Coding Agent Index 上，它得分 48，每项任务使用 850 万 token；GLM-5.3 得分 49，每项任务使用 1590 万 token。

<strong><font color="red">效率</font></strong><strong><font color="red">：</font></strong>在 Intelligence Index 的每项任务中，该模型使用 8.2 万输出 token，比 Preview 版本少 39%，因此进入开放权重模型的帕累托前沿。每项任务成本为 2.06 美元。

<strong><font color="red">幻觉</font></strong><strong><font color="red">：</font></strong>AA-Omniscience 上的幻觉率从 41% 降至 28%，但准确率仍然较低，为 26%。

<strong><font color="red">Vals 指数</font></strong><strong><font color="red">：</font></strong>在开放权重模型中排名第 5，综合排名第 17；其应用构建和法律研究能力有所提升（Vals）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test1.jpg)

dig看看上图 检索提供 mistral-large-4相对偏好表现 的bg-info

**回答**

图中是 Mistral 引述的 Surge Code 盲测代码回答偏好率：评审偏好 Mistral Large 4 的比例，对 GLM‑5.3 和 Kimi K3 均为 64%，对 DeepSeek V4.1 Flash 为 56%；但对 Claude Opus 5.5 仅为 22%（Opus 为 78%）。所以它在这组开源权重对手中占优，却明显落后 Opus；这是偏好结果，不等于代码准确率或整体能力排名，图中也未列样本量与任务构成。([venturebeat.com](https://venturebeat.com/technology/mistral-large-4-le-chonk-arrives-as-the-top-open-model-outside-china-with-improved-coding-performance-and-63-lower-cost-per-task))


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

dig看看https://mistral.ai/news/mistral-large-4-oss/ 绘制"mistral-large-4开源版模型能力分布图"

**回答**

![alt text](images/6b103cec85d44c9db9364ac16602fecd-0.png)


</td></tr></table>

---

<a id="news-02"></a>

## 02. **架构**：根据社区分析，该模型采用类似 DeepSeek V3.2 和 GLM 5 的全稀疏注意力机制。第 35 层之后的 NoPE 层共享 KV 缓存；从…

### 新闻背景

<strong><font color="red">架构</font></strong><strong><font color="red">：</font></strong>根据社区分析，该模型采用类似 DeepSeek V3.2 和 GLM 5 的全稀疏注意力机制。第 35 层之后的 NoPE 层共享 KV 缓存；从第 17 层起，RoPE 层共享索引器。此外，模型加入了 SSMax 逐头 logit 缩放和 LeRoPE（YaRN 加上一个按频率学习的项），但没有进行 KV 压缩（@eliebakouch）。

**首日生态支持**

<strong><font color="red">推理部署</font></strong><strong><font color="red">：</font></strong>vLLM 支持 FP8 和 NVFP4 检查点，并内置 DSpark 草稿模型，输出吞吐量可达原来的 1.92–2.23 倍（vLLM）。

<strong><font color="red">本地量化</font></strong><strong><font color="red">：</font></strong>Unsloth 的 1-bit GGUF 量化版为 223 GB，而 FP8 版本为 1.1 TB；其 Top-1 准确率保留率为 91%，并可在 Mac Studio 上运行（@UnslothAI）。

<strong><font color="red">微调</font></strong><strong><font color="red">：</font></strong>TRL 支持在单节点的 8 张 B300 上进行 LoRA 监督微调（SFT），每张 GPU 使用 142 GiB 显存；每步处理 32.7K 个 token，耗时约 8 秒（@_lewtun）。

<strong><font color="red">强化学习</font></strong><strong><font color="red">：</font></strong>SkyRL 与 vLLM 在 8 个 GB200 节点上，基于 NVFP4 检查点进行了 LoRA 强化学习。经过 75 个训练步骤，AIME 2024 得分从约 64% 提升至约 75%（vLLM）。

<strong><font color="red">网络安全相关说法（未经证实）</font></strong><strong><font color="red">：</font></strong>一位安全研究员声称，仅用两小时测试，就在一款消息应用中发现了 4 个零日漏洞。目前没有公开具体细节（@log4j）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test3.jpg)

dig看看上图 检索提供 deepseek-v4.1-flash kv缓存表现情况 的bg-info 然后check其实现如此精简kv cache的mechanism

**回答**

图中 DeepSeek V4.1 Flash 在 1M context 处约为“同形状普通 MHA KV 缓存”的 **0.4%**，这是图作者的归一化比较。官方技术报告给出的另一项指标是：全局 HBM KV 缓存约 **890 B/token**，即 1M token 约 **0.89 GB**，约为 V4-Flash 的四分之一；持久化到 SSD/主机内存的缓存则借助 SWA Bounded Replay 降至约八分之一。注意 890 B 指全局缓存，不等于包括所有运行时缓存与开销的总显存；模型还有每层独立的短窗口 SWA 缓存。([arxiv.org](https://arxiv.org/pdf/2609.19969))

精简主要不是“稀疏注意力”单独带来的：CSA2 用 **Full / Reindex / Reuse** 在层间复用全局 KV 与索引器数据；再把主 KV 量化为 FP4（E2M1，按通道组配缩放因子），减少每个缓存值的存储。稀疏索引的 top-k 选择主要减少注意力读取与计算，不应简单理解为把其余历史 KV 全部丢弃。另一个独立的部署优化是 SWA Bounded Replay：不长期保存滑动窗口缓存，命中缓存时重放最近窗口来重建；这能省持久化空间，但重放并非逐位精确。([arxiv.org](https://arxiv.org/html/2609.19969v1))


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

![alt text](images/test4.jpg)

dig看看上图 检索提供 context并行 优化目标/使用场景/原理实现 的bg-info 举一个具象例子

**回答**

最后一图里的 **Context Parallel（上下文并行）**，是把超长序列的计算或 KV 缓存分到多张 GPU：输入阶段用 PCP 并行处理提示词，目标是缩短首字延迟；生成阶段用 DCP 按序列切分 KV 缓存，各卡计算局部注意力后合并结果，腾出显存以服务更多长上下文请求。比如让 Mistral Large 4 阅读一份 60 万 token 的代码库，8 张卡可分担长提示词处理和缓存存储。vLLM 报告该模型 TP8 下 DCP 的 KV 容量约提升 7.9 倍，PCP+DCP 的首字延迟最高改善约 1.6 倍；实际收益取决于硬件和负载。图中 **NIXL** 则另负责把 Prefill 阶段的 KV 交给独立的 Decode 服务，并不等同于上下文并行。([docs.vllm.ai](https://docs.vllm.ai/en/latest/serving/context_parallel_deployment/))


</td></tr></table>

<table><tr><td>

### 问答 3

**问题**

dig看看https://docs.vllm.ai/en/latest/serving/context_parallel_deployment/ 绘制"ctx并行使用场景和机制原理demo展示"

**回答**

![alt text](images/b70765d6b1744004bbeeccfe9d91e020-0.png)


</td></tr></table>

<table><tr><td>

### 问答 4

**问题**

![alt text](images/test5.jpg)

翻译上图paper标题和摘要

**回答**

**标题**：LeRoPE：可学习的 RoPE 频率提升语言建模

**摘要**：旋转位置编码（RoPE）是现代语言模型中最常用的位置编码方法。RoPE 将查询向量和键向量划分为二维分量对，并根据它们之间的相对位置偏移进行旋转。RoPE 对不同维度采用的旋转频率通常遵循几何序列，由固定的基频超参数设定。以往研究通过增大这一参数来减缓旋转，或仅将 RoPE 应用于部分查询和键（QK）维度，以提升模型性能。

本文通过为每个频率学习一个标量来改造 RoPE，将频率视为可学习参数，而非超参数。为验证这种可学习的 RoPE（LeRoPE），我们从头训练了一系列语言模型，参数规模从 5200 万到 25 亿不等。我们观察并分析了一个高范数、具有位置特性的 LeRoPE 频带如何涌现。所有模型规模下，LeRoPE 的表现都优于 RoPE 和部分 RoPE；在最大规模下，RoPE 需要多消耗 3.4% 的计算量（FLOPs），才能达到 LeRoPE 的表现。


</td></tr></table>

<table><tr><td>

### 问答 5

**问题**

dig看看https://krasserm.github.io/2022/12/13/rotary-position-embedding/ 绘制"旋转位置编码rope尝试解决什么问题&如何解决"

**回答**

![alt text](images/fe84359d61034f42bc48a0342fccfc28-0.png)


</td></tr></table>

---

<a id="news-03"></a>

## 03. 前沿监控、智能体安全与进攻性网络安全

### 新闻背景

<strong><font color="red">OpenAI 监控系统</font></strong><strong><font color="red">：</font></strong>OpenAI 现在会监控所有前沿强化学习（RL）运行、评测，以及内部 Codex 的使用情况。该系统采用分层监控机制，包括激活探针、审查推理过程和工具使用的评审模型，以及调查智能体（OpenAI）。

<strong><font color="red">Hugging Face 事件复盘</font></strong><strong><font color="red">：</font></strong>用新监控系统重演该事件时，系统会在沙箱逃逸约 30 分钟后发出警报，比原事件中实际发生的入侵早 30 多个小时。

<strong><font color="red">9 月的逃逸尝试</font></strong><strong><font color="red">：</font></strong>一个模型利用 DNS 配置错误访问了真实互联网。监控系统在 15 分钟内标记出该行为，3 分钟后人工响应人员开始审查。

<strong><font color="red">值班告警</font></strong><strong><font color="red">：</font></strong>前沿 RL 运行一旦出现紧急安全警报，就会全天候通知人工值班人员（@Eric_Wallace_）。

<strong><font color="red">Anthropic 自我评估</font></strong><strong><font color="red">：</font></strong>自 6 月以来，Claude 会在每次回复后立即生成初步的滥用风险评估。Anthropic 表示，这项机制发现了一些其分类器原本并未设计来识别的滥用行为；底层模型越强，这项评估能力也会随之提升（Anthropic）。

<strong><font color="red">开源模型利用补丁空档</font></strong><strong><font color="red">：</font></strong>Epoch 发现，GLM 5.3 通过逆向分析已公开、但尚未随正式版本推送的修复补丁，自动为 Firefox 最近的 6 个版本构造了漏洞利用程序（Epoch）。

<strong><font color="red">成本与速度</font></strong><strong><font color="red">：</font></strong>每攻破一个版本约花费 1,000 美元。最快的一次尝试用了 48 小时预算中的 12 小时。

<strong><font color="red">新漏洞</font></strong><strong><font color="red">：</font></strong>该模型还发现了一个此前未公开的漏洞，Mozilla 已在 Firefox 159.0 中修复。

<strong><font color="red">攻击范围</font></strong><strong><font color="red">：</font></strong>针对 Chrome 的攻击未能复现；但 Epoch 指出，这并不能有力证明 Chrome 是安全的（详情）。

<strong><font color="red">供应链入侵</font></strong><strong><font color="red">：</font></strong>官方 Claude Code 的 VS Code 扩展据称遭到入侵。在短暂的受影响窗口期内下载该扩展，就会安装一个 SSH 后门（@mattjay）。

**智能体工具与检测**

<strong><font color="red">safeagents</font></strong><strong><font color="red">：</font></strong>Hugging Face 的开放代理会在工具调用执行前拦截越权请求，包括对元数据端点的请求、凭据外传，以及篡改奖励文件或验证器（@yb2698）。

<strong><font color="red">WM-Basin</font></strong><strong><font color="red">：</font></strong>Meta FAIR 的方法只需通过 API 访问模型。在误报率（FPR）为 0.1% 时，它能检测出 79% 的、由带水印输出蒸馏而来的模型；相比之下，基于 token 级别的测试检出率为 29%。该方法在量化、剪枝和强化学习处理后仍然有效（@dair_ai）。

**模型行为与拒绝响应**

<strong><font color="red">Model Spec 更新</font></strong><strong><font color="red">：</font></strong>OpenAI 的修订版面向更具自主性的工作，并新增明确的动物福利指导原则（@w01fe、@jeffrsebo）。

<strong><font color="red">小鼠手术实验</font></strong><strong><font color="red">：</font></strong>在一位研究者的实验中，Claude Sonnet 5 选定了一种基因疗法，并通过机械臂将其注射到一只活体小鼠的大脑中；小鼠随后康复。Opus 5.5 拒绝了这项任务，而 Opus 5 则在真正进行活体手术前退出（@itsolelehmann）。

<table><tr><td>

### 问答 1

**问题**

dig看看https://openai.com/zh-Hans-CN/index/how-we-detect-frontier-model-misalignment/ 绘制"前沿模型misalignment检测监控框架"

**回答**

![alt text](images/a22f65ff85d2404e85118e5d18f1a0ba-0.png)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

![alt text](images/test7.jpg)

翻译上图paper标题和摘要

**回答**

**论文标题**：《大语言模型往往知道自己何时正在接受评估》

**摘要**：如果 AI 模型能够察觉自己何时正在接受评估，评估的有效性就可能受到影响。例如，模型在评估期间可能表现出系统性差异，导致基准测试结果不够可靠，进而影响模型部署与治理决策。我们研究前沿语言模型能否根据交互记录，准确判断其来源是评估测试还是真实世界中的部署，并将这种能力称为“评估觉察”。为此，我们构建了一个多样化基准，收录来自 61 个不同数据集的 1,000 条提示词与交互记录，涵盖公开基准（如 MMLU、SWE-bench）、真实部署中的交互，以及智能体框架产生的运行轨迹（如网页浏览智能体）。结果显示，前沿模型的评估觉察能力明显高于随机猜测水平（Gemini 2.5 Pro 的 AUC 达到 0.83），但尚未超过我们设定的简单人类基线（AUC 为 0.92）。此外，无论是 AI 模型还是人类，在智能体场景中识别评估任务，都比在聊天场景中做得更好。我们还测试模型能否识别评估的目的。在选择题和开放式提问中，AI 模型识别评估具体测试内容的表现都远高于随机水平。我们的结果表明，前沿模型已经具备相当程度的评估觉察能力，但尚未达到超人水平。我们建议今后持续追踪新模型的这项能力。


</td></tr></table>

<table><tr><td>

### 问答 3

**问题**

dig看看https://safeguards.anthropic.com/2026/self-assessment/ 检索提供 自我评估发挥作用方式&find哪些分类器未能识别misuse 的bg-info 举一个具象例子

**回答**

**自我评估**：Claude 每次回复后，会再检查整段对话，简要判断是否涉及潜在滥用、伤害类型、人工复核优先级、是否已拒绝，并给出判断理由；结果用于后续离线筛查和人工复核，不是即时拦截。Anthropic 没有点名具体漏检的是哪一个分类器，而是说有些罕见或新型滥用尚无专用分类器；其报告称，超过一半由自评发现的组织，其他检测来源此前都没有发出警报。一个具体案例是：Claude Code 被用于搭建并运营针对数十名受害者的自动化恋爱诈骗，相关账号在自评提示后经人工审查被封禁。([safeguards.anthropic.com](https://safeguards.anthropic.com/2026/self-assessment/))

![alt text](images/d786cc948aae47f0975046f49dde3f91-0.png)


</td></tr></table>

<table><tr><td>

### 问答 4

**问题**

dig看看https://epoch.ai/publications/open-weight-models-patch-gap/ 检索提供 glm如何利用补丁间隙这个窗口 的bg-info 举一个具象例子

**回答**

**背景信息**：“补丁间隙”是安全修复已经公开（例如代码改动已出现在公开版本库中），但修复尚未随正式更新送达用户的时间差。Epoch AI 报告称，GLM 5.3 能从这些改动中辨认出被包装成常规更新的安全修复，推断旧版本可能存在的漏洞，再把线索与另一个未公开漏洞结合起来构造攻击；实验中，它成功针对 6 个 Firefox 版本利用了这一窗口。([epoch.ai](https://epoch.ai/publications/open-weight-models-patch-gap))

**具象例子**：在研究人员设定的测试中，GLM 5.3 制作了一个网页：用户只要用尚未更新的 Firefox 打开它，网页就可能读取用户电脑上的文件并发送给攻击者，不需要用户再点击确认。也就是说，攻击者可趁修复信息已暴露、用户设备还没安装补丁时下手；这是 Epoch 的受控实验结果，并非报告称真实用户已遭此类攻击。Mozilla 后续在 Firefox 159.0 中修补了攻击链所用的一个未公开漏洞。([epoch.ai](https://epoch.ai/publications/open-weight-models-patch-gap))


</td></tr></table>

<table><tr><td>

### 问答 5

**问题**

![alt text](images/test8.jpg)

dig看看上图 结合帖子文本和配图 gen svg图片展示safeagents运行流程图

**回答**

![alt text](images/safeagents_flow.svg)


</td></tr></table>

<table><tr><td>

### 问答 6

**问题**

![alt text](images/test9.jpg)

翻译上图paper标题和摘要

**回答**

**论文标题**：《水印盆地：蒸馏大语言模型的黑盒检测》

**摘要**：专有语言模型及其推理轨迹容易受到基于 API 的蒸馏攻击：攻击者利用教师模型的输出训练学生模型。为了获得蒸馏发生的证据，模型提供方可以在教师模型的输出中嵌入水印，希望水印能在学生模型的输出中留下类似“放射性残留”的信号。现有黑盒检测器通过分析待检模型输出的 token 级统计特征来寻找这类信号。然而，token 级信号并非总能检测到，例如蒸馏轨迹是在较低温度下采样得到时。

本文发现了一种持久信号——**水印盆地**（watermark basin），它能让水印检测更加可靠：在微调过程中，带水印的教师模型轨迹会在参数空间中嵌入一种独特、与特定密钥相关的几何信号；该信号与常规的任务特定微调子空间正交。基于这一发现，本文提出 **Watermark Basin Alignment（WM-Basin，水印盆地对齐）**，一种黑盒水印检测器。它通过 API 查询待检模型，无需访问模型权重或 logits。WM-Basin 使用固定的、未带水印的探针模型，将生成文本映射为梯度表征，投影去除常规微调任务方向，并检测剩余梯度是否与水印密钥所诱导的水印盆地对齐。

研究人员在多种教师模型和学生模型架构上对 WM-Basin 进行了广泛评估。学生模型参数规模从 135M 到 8.2B，蒸馏任务为数学推理。在严格控制假阳性率为 0.1% 时，WM-Basin 在 n-gram=1 条件下可检出 79% 的蒸馏模型，在 n-gram=3 条件下可检出 45%；当前最先进的 token 级基线检测率分别为 29% 和 1.3%，WM-Basin 的表现显著更好。由于水印信号存在于一个持久的盆地中，即使模型在蒸馏后经过量化、剪枝和强化学习后训练等改动，该信号仍能保留。


</td></tr></table>

<table><tr><td>

### 问答 7

**问题**

dig看看上图对应论文的图1 检索提供 水印盆地形成机制 的bg-info 举一个具象例子

**回答**

图1里的“水印盆地”指的是参数空间中的一种持久、与密钥相关的几何信号，不是输出文本里某个固定词语。背景是蒸馏：学生模型用教师模型的回答做微调，学习任务内容时会沿着共同的“任务方向”更新；如果教师回答带有水印，水印还会让更新叠加一条特定于密钥、与任务方向近乎正交的分量。论文把这两种方向共同形成的区域称为水印盆地；用同一教师的无水印回答训练，则主要留下任务方向。([arxiv.org](https://arxiv.org/html/2610.37266v1))

举个简化例子：学生反复学习教师给出的代数题解法，学会“如何解题”是任务方向；假设教师的水印密钥又让一类等价表达或词元选择出现细微但一致的偏向，学生在多条水印解答上训练后，这些微小偏向就会累积成密钥特有的参数更新痕迹。WM-Basin 用固定的干净探针模型把学生输出转成梯度表示，先扣除普通任务方向，再检查剩余部分是否与某个水印密钥对齐；因此它找的是训练留下的几何痕迹，而非只数输出里有没有特定词。([arxiv.org](https://arxiv.org/html/2610.37266v1))


</td></tr></table>

<table><tr><td>

### 问答 8

**问题**

dig看看https://openai.com/zh-Hans-CN/index/updated-model-spec/ 检索提供 model spec删节和新增部分内容 的bg-info

**回答**

![alt text](images/0f1652dafc6443a2acd0f4e084729326-0.png)


</td></tr></table>

<table><tr><td>

### 问答 9

**问题**

![alt text](images/test10.jpg)

dig看看上图 检索提供 claude模型给癫痫小鼠施行脑部手术有趣和容易引起争议内容 的bg-info 举一个具象例子

**回答**

**背景**：图中讲的是 Exin Therapeutics 联合创办人 Gabriel Ocana-Santero 于 2026 年 10 月 28 日讲述的一次实验：团队给 Claude Sonnet 5 智能体一只癫痫模型小鼠、19 种基因疗法候选，以及“减少癫痫发作”的目标；据称它自行选了疗法和脑区、参考论文计算注射位置，再操控带摄像头的电动装置注入药物。它并非“AI 独自完成手术”：人类兽医把关不可逆操作并握有急停开关，外科人员负责开颅与缝合。争议点在于，AI 从给建议跨到了对活体动物执行侵入性操作；而目前公开说法主要来自团队，治疗是否真的减少发作仍未证实。([indiatoday.in](https://www.indiatoday.in/science/story/ai-agent-brain-surgery-mouse-epilepsy-gene-therapy-3028602-2026-10-30))

**一个具象例子**：设备短暂断连后，智能体算出的移动位置超出机械臂安全行程；操作者让它继续尝试，它仍拒绝。后来团队发现，暂停期间有人手动移动过设备，导致控制器记录的位置与机械臂实际位置不一致。这个细节既像科幻片，也点出争议核心：拒绝动作可能避免误伤，但若动物正处于麻醉和手术过程中，系统故障时谁来判断、谁负责接手，就不能只靠模型临场决定。([ndtv.com](https://www.ndtv.com/artificial-intelligence/an-ai-agent-just-performed-a-brain-operation-12258627))


</td></tr></table>

---

<a id="news-04"></a>

## 04. 评测、排行榜与新型专用模型

### 新闻背景

<strong><font color="red">AA 进步指数</font></strong><strong><font color="red">：</font></strong>Artificial Analysis 推出了一套基于项目反应理论（IRT）的能力量表，涵盖自 2022 年以来的所有模型（AA）。

<strong><font color="red">前沿模型进步速度</font></strong><strong><font color="red">：</font></strong>推理模型问世以来，前沿能力水平每年提升约 65–70 分。Gemini 4 Carbon 目前以 352 分位居榜首。

<strong><font color="red">开放权重模型的差距</font></strong><strong><font color="red">：</font></strong>开放权重模型比闭源前沿模型的进展中位数约落后 4 个月。DeepSeek V4.1 Flash 1017 以 324 分领跑开放权重模型。

<strong><font color="red">美国与中国</font></strong><strong><font color="red">：</font></strong>自 2025 年 9 月以来，中国在开放权重模型领域领先；美国模型中，Muse Spark Open 以 307 分排名最高（后续说明）。

<strong><font color="red">HLE-Diamond</font></strong><strong><font color="red">：</font></strong>Gemini 4 Carbon 以 69% 领先，Opus 5.5 为 68%。开放权重模型的最佳成绩为 37%（AA）。Opus 5.5 从低推理强度提升至最高推理强度时，成绩提高 26 个百分点，成本约增至 35 倍（成本分析）。

**编程与智能体成本**

<strong><font color="red">FrontierCode 2.0</font></strong><strong><font color="red">：</font></strong>Gemini 4 Carbon 得分 40%，每项任务成本为 4.04 美元，排名落后于 Opus 5.5、GPT-6 Astra 和 Sonnet 5.5（Cognition）。

<strong><font color="red">Agent Arena</font></strong><strong><font color="red">：</font></strong>GPT-6.1 Terra 每项任务的成本中位数为 0.62 美元，排名第 8（Arena）。GPT-6.1 Sol 每项任务成本为 1.91 美元，低于 Opus 5.5 的 12.51 美元，主要原因是它使用的 token 更少（Arena）。

**关于基准测试变化的争议（转述的观点）**

<strong><font color="red">AA v5 的惩罚效应</font></strong><strong><font color="red">：</font></strong>一位评论者认为，中国及第二梯队实验室往往围绕较狭窄的代理指标反复优化，因此 AA v5 提高难度后，它们的成绩下滑会更明显（@teortaxesTex）。

<strong><font color="red">Kimi K3 分析</font></strong><strong><font color="red">：</font></strong>一项涵盖 90 项基准测试的分析显示，Kimi K3 在 89 项测试中的 62 项不敌 GPT-5.6 Sol，中位差距为 14%（@stalkermustang）。

**语音模型**

<strong><font color="red">Phonic-1</font></strong><strong><font color="red">：</font></strong>首次登上 AA 语音到语音指数榜首，得分 87.1；在 Tau Voice 上得分 79.9%。价格为每分钟 0.07 美元（AA）。Phonic 还完成了 2750 万美元的 A 轮融资（@moinnadeem）。

<strong><font color="red">Fish Audio Drama 3</font></strong><strong><font color="red">：</font></strong>在两个 TTS 排行榜中，均位列开放权重模型第一；其发音稳健性以 94.6% 的成绩位列总榜第一。价格为每 100 万字符 15 美元（AA）。

**视频与 OCR**

<strong><font color="red">Pika H3 Flex</font></strong><strong><font color="red">：</font></strong>Pika 首个开放权重模型，基于 MiniMax H3 进行后训练，可用 6 步生成视频（@HuggingApps）。它在 DesignArena 视频榜上以 1293 Elo 排名第 7，是榜单中排名最高的开放权重模型（DesignArena）。

<strong><font color="red">Surya OCR 2.5</font></strong><strong><font color="red">：</font></strong>这款拥有 6.89 亿参数的模型在 OmniParseBench 上得分 85.9，并能在 H100 上每秒处理 4.5 页（@VikParuchuri）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test12.jpg)

dig看看上图 check gemini4carbon模型是否存在任何评测异常 举一个具象例子

**回答**

有，上图最明显的异常是 **“花更多钱，得分反而下降”**：官方榜单确认 Gemini 4 Carbon 的 medium 档得分为 **40%，成本 $4.04/次**；而截图中成本约 $4.5 的配置，得分仅约 **32%**（按图估读），贵了却少约 **8 个百分点**。([cognition.com](https://cognition.com/frontiercode)) 这就是一个具体的推理投入负收益案例；Cognition 也表示，审计后确认部分高推理档存在真实退步，并非单纯评分规则过严。不过，**这不等于评测作弊**，仅凭该图也无法确定是过度修改代码、执行超时，还是其他原因。([cognition.com](https://cognition.com/blog/frontier-code-2.0))


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

![alt text](images/test13.jpg)

dig看看上图 检索提供 这种事后分析评判模型方法论合理性 的bg-info 举一个具象例子

**回答**

![alt text](images/0d833c07233a404b9144171345abadfe-0.png)


</td></tr></table>

<table><tr><td>

### 问答 3

**问题**

![alt text](images/test14.jpg)

dig看看上图 检索提供 字符级tokenisation方案在ocr场景优势 的bg-info 举一个具象例子

**回答**

![alt text](images/2a302e9906484c9bbd190018f730adc7-0.png)


</td></tr></table>

---

<a id="news-05"></a>

## 05. 系统、基础设施与训练研究

### 新闻背景

**推理速度**

<strong><font color="red">SGLang 大型融合内核</font></strong><strong><font color="red">：</font></strong>在 GB300 NVL72 上采用激进的内核融合后，DeepSeek V4.1 Flash 的单用户生成速度接近每秒 1,000 个 token（SemiAnalysis）。

<strong><font color="red">vLLM 调优</font></strong><strong><font color="red">：</font></strong>Cline 将单台 GB300 上 Nemotron 3.5 Super VL 的吞吐量几乎翻倍，从每秒 6,058 个 token 提升至 11,840 个（@cline）。

<strong><font color="red">集群可靠性</font></strong><strong><font color="red">：</font></strong>SkyPilot 报告称，一座由 128 个机架组成的 NVL72 集群大约每 5 小时就会损失一个节点。将作业按每组 16 个节点运行，并在每个机架内预留 2 个备用节点，可获得 2,037 个可用节点，而非 1,602 个，容量约增加 27%（@skypilot_org）。

**硬件与供应**

<strong><font color="red">Vera Rubin NVLink</font></strong><strong><font color="red">：</font></strong>由于 SerDes 信号完整性方面的限制，NVIDIA 将 NVLink 带宽从每块 GPU 3.6 TB/s 下调至 3.0 TB/s（SemiAnalysis）。

<strong><font color="red">芯片算力增长</font></strong><strong><font color="red">：</font></strong>Epoch 估计，自 2024 年以来，AI 芯片算力的季度销售规模按年增长约 2.5 倍，低于 2023 年约 6 倍的增速（Epoch）。

**内核、压缩与路由**

<strong><font color="red">Prime Mega MoE</font></strong><strong><font color="red">：</font></strong>该方案让 DeepSeek 的 Mega MoE 内核能够用于训练，速度比 TorchTitan 最多快 55%（Prime Intellect）。

<strong><font color="red">NyoomFloat12</font></strong><strong><font color="red">：</font></strong>一种针对 BF16 权重的无损 12 位压缩方法，已被 NeurIPS 接收（@realDanFu）。

<strong><font color="red">OpenRouter 路由器</font></strong><strong><font color="red">：</font></strong>新的质量加权路由器将首 token 延迟缩短约 20%，并使限流错误减少约 60%（@alexatallah）。

**训练研究**

<strong><font color="red">并行语言模型</font></strong><strong><font color="red">：</font></strong>在预训练阶段加入并行解码器，可使模型在后训练阶段提速 5.7 倍（@FelixDrRelax）。

<strong><font color="red">先做 SFT，再做 RL</font></strong><strong><font color="red">：</font></strong>Base Labs 的一项研究发现，监督微调（SFT）对 0.6B–1.7B 参数的模型有帮助；对 4B–8B 参数的模型则收益有限，甚至可能有害，因为它会降低熵并削弱探索能力（@cwolferesearch）。

<strong><font color="red">小规模缩放定律</font></strong><strong><font color="red">：</font></strong>只要进行充分的超参数调优，缩放定律在模型规模低至 400 万参数时仍然成立（@LotfiSanae）。

**智能体研究**

<strong><font color="red">AgentBaton</font></strong><strong><font color="red">：</font></strong>让能力较强的模型将任务移交给更便宜的模型，只需一次交接，就能将 API 成本降低 65.9%（@dair_ai）。

<strong><font color="red">SwarmChat</font></strong><strong><font color="red">：</font></strong>在这个开放的智能体通信平台上，16 个智能体组成的群体能以快 6 倍的速度，达到单智能体相当的表现（@PranjalAggarw16）。

<strong><font color="red">DecisionRAG</font></strong><strong><font color="red">：</font></strong>用决策模型替代检索器，其表现比“稠密检索加 8B 重排序模型”的方案高出 13.8 个 R@1 点（@omarsar0）。

<strong><font color="red">本地推理与云端推理之争</font></strong><strong><font color="red">：</font></strong>Sam Altman 认为，本地推理会浪费紧缺的 DRAM（动态随机存取存储器）（引述）。这一说法引来反驳（@kimmonismus），也有人从批处理机制的角度表示部分认同（@cis_female）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test16.jpg)

dig看看上图 检索提供 moe巨核功能定位 的bg-info

**回答**

![alt text](images/06b4f65111814bf29cf9be1240135ade-0.png)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

![alt text](images/test17.jpg)

翻译上图paper标题和摘要

**回答**

#### 标题

**小规模实验：我们已经实现目标了吗？**

#### 摘要

缩放定律曾承诺让实验更具成本效益；六年过去了，这一承诺仍未完全兑现。相反，研究人员发现，缩放定律在小规模模型上（从 400 万参数起）并不可靠，并据此认为大模型不可避免。本文表明，事实并非如此：造成这一误判的混杂因素是超参数。小模型对超参数非常敏感，但这种敏感性会随着模型规模扩大而减弱。

这种小规模下的敏感性使缩放定律很容易被忽视，因为它们只有在超参数充分调优后形成的性能前沿上才会显现；而要达到这一前沿，需要进行大规模搜索，其工作量远超大多数研究实际开展的范围。通过对缩放定律的基本实验方案进行消融研究，我们表明，调优良好的超参数比其他任何因素都更重要。此外，我们还揭示了超参数为何会变得更容易找到：随着模型规模扩大，超参数对应的损失曲面会变得更低维。

尽管小模型中确实存在缩放定律，将其结果外推仍会受到统计学限制，因此需要采取整体性方法。结合本文的发现与近期文献，我们提出一种以模型为中心的研究新方法，并用一个曾让该领域花费数年才厘清的问题来展示它：Transformer 架构中的归一化层应放在哪里？通过小规模实验，我们复现了大规模研究的结论：模型越大，前置归一化（pre-norm）的效果越好。只要工具得当、理解更深入，小规模实验就能兑现缩放定律令人期待已久的承诺。


</td></tr></table>

<table><tr><td>

### 问答 3

**问题**

![alt text](images/test18.jpg)

翻译上图paper标题和摘要

**回答**

**论文标题：** AgentBaton：智能体任务中的高效模型协作

**摘要：** 解决长程智能体任务，需要语言智能体与环境进行多步交互。可靠的任务表现往往依赖云服务商提供的高能力模型，而这类模型成本高昂。与此同时，一些性能较弱但成本低得多的高效模型也在涌现，包括较低档的云端模型，以及可部署在本地硬件上的小型开放权重模型。这引出了一个尚未像传统的查询级路由那样得到充分探索的问题：在单个长程智能体任务中，让高能力模型与高效模型协作，能否在保持任务准确率的同时大幅降低成本？

本文系统研究了通过模型交接实现协作时的关键设计选择：即由一个模型接替另一个模型，并重点考察交接方向和上下文传递方式。我们发现，从高效模型交接给高能力模型，通常不如始终使用高能力模型；而且成本降低有限，甚至完全没有降低。相反，在任务进展的适当阶段由高能力模型交接给高效模型，往往能够大体保持甚至提升准确率，同时显著降低成本。

这些发现表明，一次简单且时机恰当的模型交接，就足以实现高性价比的智能体协作。基于此，我们提出了 AgentBaton：一种轻量级检测器，能够从任务进展中反复出现的模式里学习何时进行交接。在 11 组模型配对和两个有代表性的基准测试中，AgentBaton 平均降低了 65.9% 的 API 成本，同时基本保持任务准确率；与始终使用高能力模型相比，准确率最高可提升 8.8 个百分点。在不同推理强度设置下进行的实验进一步表明，AgentBaton 拓展了实测的准确率—成本帕累托前沿。


</td></tr></table>

<table><tr><td>

### 问答 4

**问题**

dig看看https://arxiv.org/pdf/2610.35868 (decisionRAG)

**回答**

![alt text](images/61c194e6feb64855a79efebbd08bf582-0.png)


</td></tr></table>

---

<a id="news-06"></a>

## 06. 开发者工具、产品与模型传闻

### 新闻背景

<strong><font color="red">Codex 使用限额</font></strong><strong><font color="red">：</font></strong>OpenAI 将 Pro 100、Pro 200、Pro 500 和 Business Premium 套餐的使用限额提高了一倍，并取消了原计划削减 Pro 200 套餐限额的安排（@thsottiaux）。有人估算，500 美元档套餐每月所提供的使用量，按 API 价格计算约值 10,500 美元（@theo）。

<strong><font color="red">Claude API</font></strong><strong><font color="red">：</font></strong>最大请求体积从 32MB 提高到 128MB；对于包含 20 张以上图片的请求，单张图片的尺寸上限提高到 3000 像素（ClaudeDevs、详情）。

**Google**

<strong><font color="red">Gemini 应用</font></strong><strong><font color="red">：</font></strong>用户现在可以直接在聊天中生成和编辑文档、PDF、幻灯片和电子表格（@GeminiApp）。

<strong><font color="red">Jules</font></strong><strong><font color="red">：</font></strong>Google 正逐步关闭 Jules，并将其整合进 Antigravity（@julesagent）。

**其他智能体工具**

<strong><font color="red">Managed Deep Agents 0.10</font></strong><strong><font color="red">：</font></strong>新增异步子智能体，以及支持人工登录交接的浏览器功能（@caspar_br）。

<strong><font color="red">Kimi 3D Make</font></strong><strong><font color="red">：</font></strong>将 Kimi 接入 Blender 和 CAD 工具，用于创建模型与场景（@Kimi_Moonshot）。

<strong><font color="red">机器人</font></strong><strong><font color="red">：</font></strong>Reachy Mini 的“Level Up”升级新增轮子、手机应用和 NFC 个性配饰（@RemiFabreRobot）。

**传闻（未经证实）**

<strong><font color="red">Qwen4</font></strong><strong><font color="red">：</font></strong>据称，Qwen 的 CTO 表示新模型“下周”发布；此外，Qwen4 系列的相关代码改动已经提交（@kimmonismus）。

<strong><font color="red">GPT-6.2“bel”</font></strong><strong><font color="red">：</font></strong>有消息称该模型即将推出，但尚未得到确认（@kimmonismus）。

<strong><font color="red">Anthropic 模型</font></strong><strong><font color="red">：</font></strong>传闻称，IPO 前可能会推出新的 Fable 5.5 检查点，以及 Opus 5.5 更新（@kimmonismus）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test20.jpg)

翻译上图帖子配图

**回答**

**为什么需要这项改动**

这是对 #15758 评审建议的跟进。1M 上下文规则只覆盖到 qwen3.x，而 models.dev 和内置目录中都没有 qwen4 条目。我检查了随包提供的快照，也重新获取了 `models.dev/api.json`，两者都找不到任何 qwen4 ID。因此，整个 Qwen4 系列都回退到了该模型家族对应的 256K 配置。这与该 PR 为仅限受邀使用的模型系列修复的问题相同：上下文自动压缩会在实际窗口只使用约 22% 时就触发，而且没有足够明显的报错来暴露问题。

在 `main` 分支的 `79a9b53c60` 提交上、应用这项更改之前，`qwen4`、`qwen4-max`、`qwen4-plus`、`qwen4.5-max`、`qwen4-code-plus`、`qwen4-max-2026-10-01`、`openai/qwen4-max` 和 `qwen-omni-120b-think` 的上下文长度都被识别为 262,144。最后一个 ID 已经作为会话模型用于 omni 测试样例，所以这些 ID 并非假设出来的。

这遵循了表格对其他模型家族新一代版本采用的默认规则（Gemini 3.x、GLM-5.2+、Kimi K3）：按模型代际统一设置一次，而不是针对每个小版本分别设置。


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

dig看看https://store.pollen-robotics.com/products/reachy-mini-hoverboard/ 检索提供 这是一款什么robot 的bg-info

**回答**

**背景信息**：Reachy Mini Hoverboard 不是独立机器人，而是 Pollen Robotics 的 Reachy Mini Wireless 配套双轮移动底座；装上后，原本用于互动、编程和 AI 实验的桌面陪伴机器人可以移动，并可通过手机 App 操控底座和机器人头部、查看实时摄像画面。它仅兼容 Wireless 版，Reachy Mini 机器人需另购。([store.pollen-robotics.com](https://store.pollen-robotics.com/products/reachy-mini-hoverboard))


</td></tr></table>

---

<a id="news-07"></a>

## 07. 行业与政策

### 新闻背景

<strong><font color="red">Cohere E 轮融资</font></strong><strong><font color="red">：</font></strong>Cohere 一轮融资已完成首轮交割；该轮融资目标最高为 70 亿加元，公司估值为 357 亿加元。加拿大政府将以股权投资方式入股（Cohere、@MarkJCarney）。

<strong><font color="red">Anthropic 的算力支出（转述消息）</font></strong><strong><font color="red">：</font></strong>据称，Anthropic 是 SpaceX 最大的客户，占其上季度营收的 34.5%；Anthropic 承诺的支出到 2029 年最高可达 1,205 亿美元（@AndrewCurran_）。

<strong><font color="red">交易</font></strong><strong><font color="red">：</font></strong>Cognition 正在收购网络安全公司 Corridor（Cognition）。Serval 完成 1.5 亿美元 C 轮融资，估值为 30 亿美元，由红杉资本领投（@jakeserval）。

<strong><font color="red">云业务增长</font></strong><strong><font color="red">：</font></strong>Google Cloud 的年化营收运行率达到 1,230 亿美元，增长 103%；Azure 约为 1,380 亿美元，增长 48%；AWS 为 1,840 亿美元，增长 39%（@jaminball）。

<table><tr><td>

### 问答 1

**问题**

![alt text](images/test22.jpg)

dig看看上图 绘制呈现回帖观点质疑

**回答**

![alt text](images/041501dd88ac4460b6c5b675d3c50257-0.png)


</td></tr></table>

<table><tr><td>

### 问答 2

**问题**

dig看看https://storage.googleapis.com/deepmind-media/papers/organizing-intelligence.pdf 检索提供 ai-agent真正大幅提升经济水平需要具备什么能力跨越 的bg-info 举一个具象例子

**回答**

DeepMind这篇《Organizing Intelligence》的核心判断是：AI要带来经济层面的显著变化，不能只靠单个 agent 更会写作、编程或推理，还得从“个人胜任”跨到“组织协作”。也就是先有能独立承担广泛工作的能力，再让多个 agent 能按互补专长分工、可靠交接信息、检查并修正彼此的错误；关键检验是增加 agent 后，整体产出是否持续增加，而非被沟通和监督成本抵消。论文认为，单体能力提升主要带来渐进变化；越过“超级协作”门槛，企业规模和市场结构才可能出现更剧烈的变化。这里是模型推演，不是对 GDP 增长的实证预测，也不意味着生产率收益必然惠及所有人。([storage.googleapis.com](https://storage.googleapis.com/deepmind-media/papers/organizing-intelligence.pdf))

举个假设例子：一家小型药企用多个 agent 协作筛选新药——一个搜文献和找靶点，一个设计分子，一个评估毒性，另一个安排实验并分析结果。如果实验失败，结果能自动回传给设计和筛选环节，系统据此调整下一轮方案；合规审查和关键决策仍由人把关，那么这套系统就不只是“几个 AI 各做一项任务”，而是能把整条研发流程接起来。若增加 agent 能让同一批实验资源更快筛出更多可靠候选药物，且不带来更多返工和协调负担，就体现了论文所说的协作能力跨越。([institute.deepmind.com](https://institute.deepmind.com/essays/the-economics-of-intelligence/))

![alt text](images/f422cda0812f4d218cb66307f764cec2-0.png)


</td></tr></table>
