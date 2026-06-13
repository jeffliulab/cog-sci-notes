# Marr 三层次分析 — 理解任何信息处理系统的三个层次

> *David Marr (1982) 提出：任何完成信息处理任务的系统，都应在三个相互独立又互补的层次上分别理解——**计算理论**、**表示与算法**、**硬件实现**。这是认知科学方法论的奠基性框架，也是连接"心智"与"大脑"的桥梁。*
>
> **难度**：Intermediate　·　**阅读时间**：约 12 分钟
> **前置知识**：[认知科学基础](index.md)
> **后续阅读**：[符号主义 vs 联结主义](Symbolism_vs_Connectionism.md)、[认知的计算模型](../07_Computational_Models/index.md)

---

认知科学想解释一件看似不可能的事：一团约 1.4 公斤的湿润组织，如何"看见"、"记住"、"决定"？面对这种复杂系统，最容易犯的错误，是只在**某一个层次**上找答案——要么沉迷于神经元的电信号，要么停留在行为的描述。Marr 的贡献，是给了我们一张**把问题切成三层**的地图。读完这篇，你会得到一把贯穿整个认知科学的"分析手术刀"。

## 1. 直觉：理解一台收银机的三种问法

先从一个不吓人的例子开始。假设你想彻底"看懂"一台收银机。你会发现，你其实在问三个层次完全不同、却都成立的问题：

1. **它在算什么？为什么？** —— 它把一堆商品价格映射成总价，本质就是"加法"。为什么偏偏是加法？因为现实世界有个硬约束：买两组商品的总价，必须等于分别买的总价之和。是这个约束"逼"出了加法的代数结构。
2. **它用什么步骤算？** —— 是逐位竖式进位，还是查一张大表，还是把数转成二进制再相加？
3. **它用什么材料实现？** —— 机械齿轮、算盘珠，还是硅晶体管？

三个问题指向同一台机器，却**谁也替代不了谁**：知道它内部是齿轮（材料），完全不告诉你它在算加法（任务）；知道它算加法，也不告诉你它用竖式还是查表（步骤）。

Marr 的核心主张就是：**理解大脑与心智，必须同样地分这三层来问。** 把三层混作一谈，正是许多争论无解的根源。

## 2. 形式化定义

把上面的直觉拧紧成定义。我们把任何系统都看作在实现某个**从输入到输出的映射** $f: X \to Y$。Marr 的三层次 (**Marr's Three Levels of Analysis**) 分别回答关于这个 $f$ 的不同问题：

- **计算理论层 (Computational Theory, CT)**：系统计算的究竟是哪个函数 $f$，以及**为什么**这个 $f$ 对它所处的环境是恰当的（目标是什么、有哪些约束、问题是否可解）。回答 *What & Why*。
- **表示与算法层 (Representation & Algorithm, RA)**：输入 $X$ 与输出 $Y$ 用什么**表示** $R_X, R_Y$ 来编码，又用什么**算法** $A$ 把前者变成后者。回答 *How*。形式上要求 $A: R_X \to R_Y$ 能正确算出 $f$。
- **实现层 (Implementation, IM)**：算法 $A$ 最终跑在什么**物理基质**上——神经元、硅片、还是齿轮。回答 *Physically realized by what*。

一个**完整**的解释，要求三层彼此对得上：

$$
\underbrace{f: X \to Y}_{\text{CT：算什么}}
\;\;\xrightarrow{\text{选择表示与算法}}\;\;
\underbrace{A: R_X \to R_Y}_{\text{RA：怎么算}}
\;\;\xrightarrow{\text{物理实现}}\;\;
\underbrace{\text{neurons / silicon}}_{\text{IM：用什么算}}
$$

注意箭头方向：上层**约束**下层（任务规定了算法的目标，算法规定了硬件要支持什么），但同一上层可以由很多种下层来满足——这一点是后面所有讨论的关键。

## 3. 历史与动机

这套框架不是凭空来的，它诞生于一场具体的科学困境。

David Marr 是 MIT 的神经科学家，主攻视觉。他与 Tomaso Poggio 合作（Marr & Poggio, 1976/1977）时观察到，当时的视觉研究陷在两个极端：一派只盯着单个神经元什么时候放电（纯实现层），另一派只描述行为现象（接近计算层）却从不追问中间的机制。两边都觉得自己在"解释视觉"，却谁也说服不了谁。

Marr 给了一个著名的类比来点破僵局：**你无法仅凭羽毛的微观结构去理解"飞行"——飞行的"计算理论"是空气动力学。** 同理，仅有神经元的接线图，也理解不了视觉。每个层次都缺一不可，但又各管一段。

1980 年，Marr 因白血病英年早逝，年仅 35 岁。他的遗著《**Vision**》(1982) 系统地写下了这套三层次框架，此后成为认知科学与计算神经科学**共享**的方法论基石。

## 4. 三层次详解

定义有了，我们来把三层摊开看清楚，再追问它们之间到底是什么关系。

### 4.1 三层的内容与典型问题

<div class="diagram">
<svg viewBox="0 0 720 300" xmlns="http://www.w3.org/2000/svg" font-family="Georgia, serif">
  <rect x="120" y="20" width="480" height="64" rx="6" fill="var(--dia-accent-soft, rgba(196,103,58,.10))" stroke="var(--dia-accent, #c4673a)" stroke-width="1.5"/>
  <text x="360" y="46" text-anchor="middle" font-size="17" fill="var(--dia-accent, #c4673a)" font-weight="bold">计算理论 Computational Theory</text>
  <text x="360" y="68" text-anchor="middle" font-size="13" fill="var(--dia-stroke-soft, #6b5f4e)">算什么 / 为什么 — 目标、约束、可解性</text>
  <rect x="120" y="118" width="480" height="64" rx="6" fill="none" stroke="var(--dia-blue, #2c4d6e)" stroke-width="1.5"/>
  <text x="360" y="144" text-anchor="middle" font-size="17" fill="var(--dia-blue, #2c4d6e)" font-weight="bold">表示与算法 Representation &amp; Algorithm</text>
  <text x="360" y="166" text-anchor="middle" font-size="13" fill="var(--dia-stroke-soft, #6b5f4e)">怎么算 — 输入/输出表示 + 算法</text>
  <rect x="120" y="216" width="480" height="64" rx="6" fill="none" stroke="var(--dia-green, #4a6741)" stroke-width="1.5"/>
  <text x="360" y="242" text-anchor="middle" font-size="17" fill="var(--dia-green, #4a6741)" font-weight="bold">实现 Implementation</text>
  <text x="360" y="264" text-anchor="middle" font-size="13" fill="var(--dia-stroke-soft, #6b5f4e)">用什么算 — 神经元 / 硅 / 齿轮</text>
  <line x1="360" y1="84" x2="360" y2="116" stroke="var(--dia-stroke-soft, #6b5f4e)" stroke-width="1.2" marker-end="url(#a)"/>
  <line x1="360" y1="182" x2="360" y2="214" stroke="var(--dia-stroke-soft, #6b5f4e)" stroke-width="1.2" marker-end="url(#a)"/>
  <defs><marker id="a" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto"><path d="M0,0 L8,4 L0,8 z" fill="var(--dia-stroke-soft, #6b5f4e)"/></marker></defs>
</svg>
</div>
<p class="figure-caption">Figure 1 — Marr 三层次：上层规定"算什么"，中层规定"怎么算"，下层规定"用什么算"；同一上层可由多种下层实现。</p>

把它落到两个你熟悉的系统上，三层的分工就一目了然：

| 层次 | 核心问题 | 视觉系统的例子 | 深度学习的例子 |
|---|---|---|---|
| 计算理论 | 算什么、为什么 | 从二维图像恢复三维结构（为什么可能：世界有规律性约束） | 最小化哪个损失函数、为什么这个目标合理 |
| 表示与算法 | 怎么算 | 边缘检测 → 2.5D 草图 → 3D 模型 | Transformer 架构、反向传播 |
| 实现 | 用什么算 | 视网膜 + V1 + 腹侧通路 | GPU、浮点权重矩阵 |

读这张表时请留意：**同一行换一列，另外两层不一定要变。** 这正引出下一个关键问题。

### 4.2 层次之间是什么关系？——半独立性

最常被误解的，就是三层的关系。先说独立的一面，这一面有个专门的名字：**多重可实现性 (Multiple Realizability)**。

它的意思是：同一个计算 $f$ 可以由多种算法实现，同一种算法又可以由多种硬件实现。"算加法"这件事，根本不在乎你用齿轮还是硅。推到大脑上，这就有了一个深刻的推论——**心智的功能描述（计算层 / 算法层）不能被简单地还原为神经机制（实现层）**。这正是认知科学敢于作为一门独立学科存在的根基：研究"心智在算什么"，不必等神经科学先把每根神经元数清楚。

但故事还有另一面。三层并非**完全**独立：**实现层会反过来约束算法层。** 大脑高度并行、单元很慢、还极度受能耗限制——这些硬件事实，逼出了与串行数字计算机非常不同的算法（比如群体编码、近似推断，而不是精确串行计算）。所以成熟的认知科学并不主张"严格自上而下推导"，而是把三层看作**互相约束、协同建模**的整体。一句话：上层给方向，下层给现实。

## 5. Worked Example：把"加法"拆到三层

抽象讲完，我们回到收银机，用 Marr 本人最爱的例子——加法——一步步走一遍，你会真切感到"换一层不动另一层"。

- **计算理论层**：函数 $f(a, b) = a + b$，定义在整数上，满足交换律 $a+b=b+a$、结合律、有单位元 $0$。"为什么是这个 $f$"——因为它刻画了"把两堆东西合并后再数"这个现实任务，它的代数性质完全由现实约束决定，而不是由我们怎么实现它决定。
- **表示与算法层**：同一个加法，可以有完全不同的算法：
  - 阿拉伯数字 + 逐位进位；
  - 罗马数字（表示一换，进位算法立刻变得很笨拙）；
  - 二进制补码 + 全加器逻辑。
  三者**表示/算法各不相同，算的却是同一个 $f$**。
- **实现层**：又可以换上各种物理基质：十进制机械齿轮（老收银机）、硅加法器（CPU）、算盘珠，乃至人脑顶内沟里的数量表征。**实现不同，算法可以完全一样**。

把这三步连起来看，结论非常干净：**换实现不改算法，换算法不改计算**——三层各自独立可换。这就是多重可实现性的"手感"。

## 6. Common Pitfalls

理解了正面，我们看几个最常踩的坑——它们几乎是认知科学讨论里反复出现的误区。

> **易错点 1：以为三层严格自上而下、互不影响。** Marr 早期叙述确实偏自上而下，但成熟观点承认实现会约束算法（生物硬件的并行性塑造了大脑的算法）。三层是互相约束的，不是单向瀑布。
>
> **易错点 2：把算法层和实现层混为一谈。** "用了 Transformer"是算法层的事；"跑在 A100 上、权重是 bf16"是实现层的事。换块 GPU，算法一点没变。
>
> **易错点 3：以为深度学习"只是实现层"的事。** 大错：损失函数与任务设定属计算层，网络架构与优化算法属算法层，硬件与数值才是实现层。把三层混在一起，"模型到底在学什么"这个问题就无从谈起了。

## 8. Related Concepts

- **前置**：[认知科学基础](index.md) — 三层次是认知科学"多层次解释"立场的核心。
- **横向**：[符号主义 vs 联结主义](Symbolism_vs_Connectionism.md) — 这场经典争论，很大程度上就是"在算法层用什么表示"之争。
- **后续**：[认知的计算模型](../07_Computational_Models/index.md) — 计算建模，就是显式地在算法层把一个计算理论"落地"。
- **跨板块（神经科学）**：[计算神经科学](/notes/neuroscience/05_Computational_Neuroscience/index) — 它正是用 Marr 框架，把神经机制与计算目标对接起来。
- **跨板块（湿件计算）**：[湿件计算导论](/notes/wetware/00_Foundations/Overview) — 活体神经元"算什么"（计算层）独立于它是碳基还是硅基（实现层），这正是多重可实现性在生物计算里的回响。

## References

1. Marr, D. (1982). *Vision: A Computational Investigation into the Human Representation and Processing of Visual Information*. W. H. Freeman.（第 1 章系统提出三层次）
2. Marr, D., & Poggio, T. (1976). *From Understanding Computation to Understanding Neural Circuitry*. MIT AI Memo 357.
3. Poggio, T. (2012). *The Levels of Understanding framework, revised*. Perception, 41(9), 1017–1023.
4. Bechtel, W., & Shagrir, O. (2015). *The non-redundant contributions of Marr's three levels of analysis for explaining information-processing mechanisms*. Topics in Cognitive Science, 7(2), 312–322.
