# Smart Ring Copywriting Skill

> 智能戒指 / 健康穿戴品类的「卖点文案 Guideline + 速评卡 + 改稿法则」，打包成一个 Claude Skill。
> 让 AI 按同一套标准写标题、打分、改稿——不用每次从零调教。

![version](https://img.shields.io/badge/version-0.3.0-blue)
![platform](https://img.shields.io/badge/Claude-Skill-8A5CF6)
![category](https://img.shields.io/badge/category-smart%20ring%20%2F%20wearable-teal)

---

## 这是什么

一个把**品类级文案规范**装进 AI 的 Skill。装上之后，Claude 不再写 "Thrive."、"Made for you."、"Bidirectional Adaptive Fit" 这类空话和工程师话，而是按一套可打分的标准产出北美语境下的功能型文案。

覆盖的文案类型：标题、小标题、一句话卖点。适用版位：详情页、视频字幕、Meta / TikTok 广告、EDM 主题行、Google 搜索标题、落版。

这不是灵感工具，是**验收工具**。它同时回答两个问题：

1. 这句文案好不好？——5 问打分，满分 10，附一票否决项
2. 不好在哪、怎么改？——固定诊断输出格式，3 个改写版本

## 解决什么问题

文档把品类文案的失败总结成四类：

| 失败类型 | 表现 |
|---|---|
| **空** | 读完不知道卖什么：*Thrive. / Made for you.* |
| **平** | 像说明书：*2.23mm Titanium Smart Ring with 7 Day Battery* |
| **工程味** | 内部技术词上标题：*Bidirectional Adaptive Fit* |
| **学舌** | 照搬竞品，没有自己的卖点 |

对应的解法是四层规则：信息结构 → 六个公式 → 去工程师语言 → 打分与改写。

## 核心设计

**铁律**：功能是内容，表达是包装。信息直给，句子好读，用户的话，不是工程师的话。

**四个拆解测试**（写和改任何一句之前）：

1. 去掉修辞，信息还在吗？（在才合格）
2. 去掉信息，只剩修辞吗？（是就不合格）
3. 换成竞品名字还成立吗？（成立就没差异化）
4. 删掉这个词，用户少知道什么吗？（没少，这个词就该删）

**六个公式**（从 Insta360、Anker 的标题模式归纳）：

| # | 公式 | 智能戒指示例 |
|---|---|---|
| F1 | 一个数字当主角 | *Just 2.23mm Thin* |
| F2 | 一个动作，一个结果 | *Wear It. Get Your Recovery Score.* |
| F3 | 痛点 → 解法 | *Ring Too Tight at Night? It Adapts.* |
| F4 | 证据贴身 | *Tested Against Hospital ECG* |
| F5 | 省掉了什么 | *No Subscription. No Start Button.* |
| F6 | 新旧对比 | *Fixed-Size Rings Squeeze. This One Adapts.* |

**5 问速评卡**（每个"是"得 2 分）：

1. 一眼懂：3 秒内能说出讲的是哪个功能？
2. 有硬信息：有数字、功能名或证据？
3. 有好处：看得出"对我有什么用"？
4. 不通用：换成竞品名字就不成立？
5. 说人话：北美人会这么说？没有工程师词、翻译腔？

**5 条一票否决**：一个标题讲 2 个以上卖点 / 出现禁用词（含工程师语言）/ 慎用项无证据 / 文字与画面对不上 / 小标题重复标题。

## 仓库结构

```
smart-ring-copywriting-skill/
├── SKILL.md                          # 技能主文件：角色、四种工作模式、核心规则、评分流程
├── references/
│   ├── guideline.md                  # Guideline 全文：完整禁用表 / 慎用表 / 词汇分级 / 翻译公式
│   ├── scoring-card.md               # 速评卡全文：校准示例、完整诊断示例、发稿前自检
│   ├── revision-playbook.md          # 改稿法则：10 条修改动作 + 改稿顺序 + 正文审稿三问
│   ├── brand-circul-3.md             # CIRCUL 3 品牌事实标尺：参数 / 术语表 / 已批准标准句 / 红线
│   └── brand-profile-template.md     # 品牌档案模板：数据口径表 / 差异化支点 / 视频镜头表
├── CHANGELOG.md
└── README.md
```

SKILL.md 是速查和操作流程；写文案或打分需要查完整表时，会按引用去读 `references/` 对应文件。品牌专属的事实（参数、证据、价格口径）放在品牌档案里，与规则分离，换品牌只换档案。

## 安装

### 方式一：Claude Code / Claude 桌面版（推荐）

把仓库克隆到个人 skills 目录：

```bash
git clone https://github.com/blueelf1988/smart-ring-copywriting-skill.git \
  ~/.claude/skills/smart-ring-copywriting
```

之后在任何会话里说「用速评卡给这条标题打分」即可触发。

### 方式二：手动上传

在 Claude 的 Skills 设置里新建名为 `smart-ring-copywriting` 的 skill，把 `SKILL.md` 全文粘贴进指令，`references/` 三个文件放到 skill 目录下（或按需粘贴给 Claude）。

### 方式三：临时使用

把 `SKILL.md` 直接拖进对话，让 Claude 按其中的流程执行。适合一次性诊断，不会常驻。

## 使用示例

### 写：给卖点出三版

```
用智能戒指文案 skill 写一条标题：
卖点 [自适应伸缩]，事实 [6 个尺码、相邻重叠 3mm]，
渠道 [视频字幕，伸缩结构镜头]，要 F3 和 F6 各一版。
```

### 评：给一条文案打分

```
按速评卡打分：
"Bidirectional Adaptive Fit / Expands and contracts with your finger."
```

输出（固定格式）：

```
文案：Bidirectional Adaptive Fit / Expands and contracts with your finger.
版位：视频伸缩结构镜头
得分：6 / 10（一眼懂 2　硬信息 2　好处 2　不通用 0　说人话 0）
一票否决：第 5 条（小标题已经讲了"双向"，标题再说是重复）
问题：标题里的 Bidirectional 是结构术语，对用户没有额外信息
工程师词检查：有 → Bidirectional（建议删）
改写：
  1. 直白款：Adaptive Fit / Expands and contracts with your finger.
  2. 表达款（F6）：Fixed Rings Squeeze. This One Adapts. / Expands and contracts with your finger.
  3. 备选（F3）：Ring Too Tight at Night? It Adapts. / Flexes as your finger changes.
待确认：无
```

去掉 *Bidirectional* 后升至 8 分——和 *Fixed Rings Squeeze. This One Adapts.*（10 分）的差距，就是「差异化」与「钩子」。

### 批量：整套文案体检

```
这是 13 个镜头标题，按速评卡逐条打分，汇总成表，标出重复卖点，
最后列出最该优先改的 3 条：[粘贴表格]
```

### 改：审稿改稿（0.2.0 新增）

```
按改稿法则审这篇产品页文案，输出修改清单（原句→改后→法则→原因）+ 改后全文：
[粘贴文案]
```

改稿法则归纳自专业文案对真实产品页的 50 余处校正，核心是把改稿当成质检而不是润色，顺序固定：**事实 → 术语 → 动词 → 句法 → 节奏**。十条动作包括：宣称对事实（removes sizing risk → adjusts within the selected size range）、术语治理（Everyday Recovery → Daily Recovery）、动词治理（Explore → Understand）、名词化拆解（a fresh size check → checking the fit again）、句法衔接（with steady breathing → and breathing remains steady）、冗余内消、数字前置、因果校对、合规语气、标题命名。完整对照表见 `references/revision-playbook.md`。

### 打分档位

| 得分 | 处理 |
|---|---|
| 9–10 | 直接出稿 |
| 7–8 | 小修后出稿或做 A/B |
| 5–6 | 按失分项重写 |
| ≤ 4 | 推翻重来 |

## 定制到你的品牌

`references/brand-profile-template.md` 里有三张表：数据口径表、差异化支点表、视频镜头标题表。三张表都填了，AI 写文案时就不会编数字、不会拿竞品也有的卖点当差异点。

原则：档案里标 `⚠️ 需确认` 和 `❌ 待定` 的项，不进入最终文案。公开仓库里的模板是脱敏版，真实口径请放团队内部副本。

## 适合谁

- 智能戒指 / 健康穿戴品类的 DTC 品牌运营、内容负责人
- 代运营 / 广告代理商里做健康穿戴客户的策划、文案
- 需要给 AI 定一条稳定文案底线的人（不想每次重新纠正「别写 Next-Gen」）

## FAQ

**只适用于智能戒指吗？**
五问评分、一票否决、删除测试、六个公式适用于任何健康穿戴品类；工程师词表和示例是智能戒指专属，换品类需要替换 `references/guideline.md` 第 5 节。

**是英文文案工具吗？**
是。它规定的是**面向北美消费者的英文文案**怎么写。内部沟通、中文方案仍可用中文。

**能用来审别人的稿吗？**
可以，打分流程不依赖作者。把它当评审标准用，输出格式固定，便于横向比较多条文案。

**会替我编产品参数吗？**
不会。没填品牌档案、没提供事实时，缺的数字会被标成「待确认」而不是编造。

## 版本

当前 0.3.0（2026-11-04）。版本号规则 `0.MINOR.PATCH`，每次更新同步写 [CHANGELOG.md](CHANGELOG.md)。

0.3.0 新增 `brand-circul-3.md`（CIRCUL 3 品牌事实标尺，含 10 ATM 口径）；0.2.0 新增改稿法则（`revision-playbook.md`）；0.1.0 为首版（Guideline + 速评卡）。

## 作者

Leo — 跨境电商品牌运营，CIRCUL 智能戒指品牌。

许可以开源协议为准，默认建议 MIT；如需其他协议请在仓库内自行添加 LICENSE 文件。
