# Vibe Coding 指南：WorkBuddy 与 Codex 双平台技能实战

---

## 目录

- [一、什么是 Vibe Coding](#一什么是-vibe-coding)
- [二、两大平台对比：WorkBuddy vs Codex](#二两大平台对比workbuddy-vs-codex)
- [三、WorkBuddy 最值得推荐的 15 个技能](#三workbuddy-最值得推荐的-15-个技能)
- [四、Codex 最值得推荐的 15 个 Skill](#四codex-最值得推荐的-15-个-skill)
- [五、通用方法论：技能是可带走的资产](#五通用方法论技能是可带走的资产)
- [六、上手路线建议](#六上手路线建议)
- [七、注意事项与避坑](#七注意事项与避坑)

---

## 一、什么是 Vibe Coding

一句话：**用自然语言指挥 AI 编程，你描述想要什么，AI 负责实现**。

- 你不需要懂变量声明、函数调用、数据库连接，只需要把需求描述清楚；
- 核心闭环是「描述 → 生成 → 测试 → 反馈」：跑通了就过，跑不通就换个说法再试；
- 对程序员是提效工具，对非程序员是直接把「原本过不去的坎」铲平——把想法变成能跑的产品；
- Skill（技能）是 Vibe Coding 的能力放大器：**一份说明书教 AI 一项新本事**——写代码前先出计划、报错了自动排查、替你操作浏览器。裸的 AI 像个聪明但两手空空的实习生，装上技能，就像给了他一柜子趁手的工具。

**2026 年的关键变化**：如果说 2023–2025 年属于 AI 大模型，2026 年必然属于 AI 智能体（Agent）。国内代表是 WorkBuddy，国外代表是 Codex，两者都以「Skill 生态」为核心玩法。

---

## 二、两大平台对比：WorkBuddy vs Codex

| 维度 | WorkBuddy | Codex |
|---|---|---|
| 出品方 | 腾讯（由 CodeBuddy Work 更名而来） | OpenAI（已并入新版 ChatGPT 桌面端） |
| 目标用户 | 普通用户、非技术人群、职场人士 | 开发者、进阶用户 |
| 技能市场规模 | SkillHub 超 7 万个社区技能、3000 万次下载（大卖场） | 官方精选区（curated）39 个精选技能（精品店） |
| 技能安装方式 | 自然语言安装：「帮我安装这个技能：\<URL\>」 | `$skill-installer <技能名>` 或 `npx skills add ...` |
| 技能存放位置 | 技能市场一键安装 / GitHub URL 安装 | `~/.codex/skills/`（全局生效）；`.codex/skills/` 或 `.agents/skills/`（仅当前项目） |
| 生态特点 | 数量大、覆盖办公/学习/求职/创作等日常场景 | 官方 39 个个个能打，走 agentskills.io 开放标准 |
| 双方共同点 | SKILL.md 是通用标准，Claude Code、Codex、WorkBuddy、Cursor 认的是同一份文件 | 同左 |

**Codex 技能机制速览**：
- 一个 skill = 一个文件夹，里面一份 `SKILL.md`（名字、用途、执行流程）+ 可选的脚本和参考文件；
- Codex 启动时把每个技能的名字和描述预加载进系统提示词，干活时自己判断用哪个；
- 装完问一句 **"你现在有哪些技能"**，识别了才算装上；
- 官方技能目录在 [openai/skills](https://github.com/openai/skills)，系统内置区五个技能随 Codex 自动安装。

---

## 三、WorkBuddy 最值得推荐的 15 个技能

按四大方向分类：**研究与信息处理（3）、学习与知识管理（2）、职场办公与求职（4）、视觉创作与演示设计（6）**。

> 安装方式统一：直接对 WorkBuddy 说「帮我安装这个技能：\<URL\>」。

### （一）研究与信息处理

#### 1. Deep Research（深度研究）
- **解决什么**：搜出来的资料多而杂，网页、文章、视频、帖子混在一起，难以整理成有依据的报告。
- **能力**：把大问题拆成多个小问题 → 查找资料 → 判断来源 → 提取事实 → 对比核对 → 产出带引用的调研报告（8 步法）。
- **示例**：「深度调研 2026 年普通人最值得付费的 AI 工具有哪些，给出来源、对比表和最终结论。」
- **安装**：https://github.com/wshuyi/deep-research

#### 2. Last 30 Days（过去 30 天发生了什么）
- **解决什么**：普通搜索结果多是几个月甚至几年前的旧文，看不出话题最近的动态。
- **能力**：搜索多个平台过去 30 天的内容，结合点赞、评论、观看等互动数据，整理成近期简报；也可查公司、产品、人物或具体事件。
- **示例**：「/last30days 最近 30 天 AI Agent 领域最受关注的话题是什么？」
- **安装**：https://github.com/mvanhorn/last30days-skill

#### 3. Research-to-Diagram（调研结果画成关系图）
- **解决什么**：调研完还要重新整理人物关系、事件关系或技术结构，手动画图慢且不一定清楚。
- **能力**：给它一个主题，先整理资料和关系，再生成可视化关系图谱（人物关系、历史事件、知识分类、技术架构）。
- **示例**：「深度调研《红楼梦》人物关系，生成关系图谱，并附上参考来源。」
- **安装**：https://github.com/wshuyi/research-to-diagram

### （二）学习与知识管理

#### 4. IMA 知识库
- **解决什么**：资料已存进笔记软件，但 AI 看不到里面的内容，查资料、整理笔记都要重新复制粘贴。
- **能力**：让 AI 读写你的 ima 笔记和知识库——搜索资料、整理笔记、上传文件、添加链接，或基于知识库内容生成新清单和文章。
- **示例**：「搜索一份日本关西 5 日游的旅行攻略，存到我的 ima 知识库，并整理成一篇笔记。」
- **安装**：https://app-dl.ima.qq.com/skills/ima-skills-1.1.9.zip
- **备注**：安装后需提供密钥，在 ima 知识库的「Claw 配置」里获取。

#### 5. Obsidian Skills
- **解决什么**：让 AI 写 Obsidian 笔记时，双链、Properties、Bases 或 Canvas 格式经常写错，还得自己修。
- **能力**：按 Obsidian 的规则管理知识库——创建/修改笔记、建立双链、生成数据视图、绘制 Canvas 画布、网页内容整理存档。
- **示例**：「搜索一下 Raycast 的最佳实践教程，整理成 Markdown，保存到我的 Obsidian 知识库，并和已有笔记建立双链。」
- **安装**：https://github.com/kepano/obsidian-skills
- **备注**：这是技能集合，安装后按需开启子技能即可，不必全部使用。

### （三）职场办公与求职

#### 6. Ego Lite（浏览器技能）
- **解决什么**：很多事必须打开浏览器才能做（登录、点击、填表、复制数据、截图），AI 只读网页不够，每步自己操作又麻烦。
- **能力**：让 WorkBuddy 真正使用浏览器——打开网页、点击元素、填写内容、提取数据、截图，可用浏览器里的登录状态（技能列表中显示为 `ego-browser`）。
- **示例**：「打开黄金价格的行情页面，提取最近 30 天的金价，整理成表格。」
- **安装**：https://github.com/citrolabs/ego-lite
- **备注**：涉及登录、填写和提交时，按 WorkBuddy 提示确认操作。

#### 7. AI 简历助手 Skill
- **解决什么**：实习、项目、比赛等经历散落在聊天记录、笔记和旧简历里，每投一个岗位就要重改一遍，排版还容易乱。
- **能力**：根据目标岗位重新组织经历，生成一页 A4 简历，多套模板，输出 HTML 和 PDF（技能列表中显示为 `html-resume-builder`）。
- **示例**：「搜索数学家王虹的公开资料，整理成一页学术简历，突出教育背景、研究方向和主要成就，最后导出 PDF。」
- **安装**：https://github.com/KevinYoung-Kw/vibe-resume-skill

#### 8. Kami 纸张 Skill
- **解决什么**：内容写完了，但简历、白皮书、作品集还要重新排版，导出 PDF 容易出字体和版式问题。
- **能力**：把 Markdown 内容排成正式文档，多套设计模板，适合投递、分享和打印，支持中/英/日文材料，侧重排版和纸张质感。
- **示例**：「搜索数学家王虹的公开资料，整理成一页学术简历，……输出 Kami 纸张风格的 PDF。」
- **安装**：https://github.com/tw93/kami
- **备注**：与简历助手的对比——简历助手侧重内容组织和求职场景，Kami 侧重排版和纸张质感。

#### 9. WPS 操作 Skill
- **解决什么**：AI 能写文字，但写完还得自己打开 WPS 复制到 Word/Excel/PPT，手动调格式、做表格、画图。
- **能力**：用自然语言操作 WPS 办公软件——WPS 文字、表格、演示，文档格式调整、表格整理、PPT 内容生成、跨应用处理。
- **示例**：「搜索 2025 年国内新能源汽车的月销量数据，整理成 WPS 表格，并生成一页带柱状图的 WPS 演示。」
- **安装**：https://github.com/lc2panda/wps-skills

### （四）视觉创作与演示设计

#### 10. Frontend Slides（前端幻灯片设计）
- **解决什么**：普通 PPT 模板千篇一律，自己不会设计，选不好颜色、字体和版式。
- **能力**：先看视觉方案再做网页幻灯片——先生成几版不同风格的网页 slides 预览，选定方向后生成单文件 HTML，可继续导出 PDF。
- **示例**：「搜索人工智能发展史的资料，整理成大纲后做成一套网页幻灯片，先给我三个不同风格的预览。」
- **安装**：https://github.com/zarazhangrui/frontend-slides

#### 11. 归藏 PPT
- **解决什么**：文章、Markdown 或产品文档写好了，做成演示文稿还要重新想封面、配色、图片和布局。
- **能力**：把文字内容直接变成网页幻灯片——自动处理版式、配图、封面和横向翻页，生成可直接打开的单 HTML 文件，提供电子杂志风和瑞士风两种风格。
- **示例**：「搜索关于敦煌莫高窟的科普资料，做成电子杂志风的横向网页 PPT，生成单个 HTML 文件。」
- **安装**：https://github.com/op7418/guizang-ppt-skill

#### 12. Excalidraw 绘图 Skill
- **解决什么**：流程、架构、人物关系用文字难讲清，手动画图慢，AI 生成普通图片又不能继续编辑。
- **能力**：用自然语言生成**可编辑**的 Excalidraw 图表——流程图、关系图、思维导图、系统架构图（技能列表中显示为 `excalidraw-diagram`）。
- **示例**：「搜索外卖平台的典型系统架构，用 Excalidraw 画一张架构图，区分前端、后端、数据库和外部服务。」
- **安装**：https://github.com/coleam00/excalidraw-diagram-skill

#### 13. Bento（单文件幻灯片工具）
- **解决什么**：传统 PPT 要装专门软件才能打开，分享后容易出现版本和字体问题。
- **能力**：一个文件完成幻灯片编辑和演示——浏览器中运行的单文件幻灯片工具，无需安装软件，可编辑、分享、播放（技能列表中显示为 `bento-slides`）。
- **示例**：「搜索解放战争经典战役回顾，整理成大纲，用 Bento 做成一套可以继续修改的单文件幻灯片。」
- **安装**：https://github.com/nyblnet/bento

#### 14. HTML Anything（杂志/演示/海报设计）
- **解决什么**：想做海报、杂志风图文或社交卡片，不会设计、套模板千篇一律，做出来总有「凑合感」。
- **能力**：内置 **75 种专业模板**，一键把 Markdown 变成杂志、演示文稿、海报、社交媒体卡片（小红书封面、推文卡片都能做）；本地运行无需配置 API Key，HTML 可直接打开、导出图片，内容一键发布到公众号、知乎等平台。
- **示例**：「搜索最近关注度最高的 AI 新闻，做成一份杂志风的图文页面，再生成一张配套的小红书封面卡片。」
- **安装**：技能市场直接搜 `html-anything` 一键安装；或 https://github.com/nexu-io/html-anything

#### 15. 女娲 Skill（人物思考框架）
- **解决什么**：复杂问题上普通 AI 建议很通用，缺少明确判断框架；想知道乔布斯、费曼、张雪峰会怎么分析，却不知道怎么提问。
- **能力**：把人物的心智模型、决策方法和表达特点整理成可调用的视角——不是模仿语气，而是用对方的思考方式分析新问题（技能列表中显示为 `huashu-nuwa`）。
- **示例**：
  - 「蒸馏张雪峰的思考框架。」
  - 「用张雪峰的视角帮我分析：孩子高考报志愿，计算机和临床医学该怎么选？」
  - 「费曼会怎么给小学生解释下雨是怎么回事？」
- **安装**：https://github.com/alchaincyf/nuwa-skill

### WorkBuddy 15 技能速查表

| # | 技能 | 一句话 | 来源 |
|---|---|---|---|
| 1 | Deep Research | 8 步法深度调研，产出可追溯的调研报告 | [GitHub](https://github.com/wshuyi/deep-research) |
| 2 | Last 30 Days | 搜过去 30 天跨平台真实讨论，出近期简报 | [GitHub](https://github.com/mvanhorn/last30days-skill) |
| 3 | Research-to-Diagram | 深度调研后生成可视化关系图谱 | [GitHub](https://github.com/wshuyi/research-to-diagram) |
| 4 | IMA 知识库 | 连接 ima 笔记与知识库，读写和检索资料 | [下载地址](https://app-dl.ima.qq.com/skills/ima-skills-1.1.9.zip) |
| 5 | Obsidian Skills | 写笔记、建数据视图、画关系图、抓网页存档 | [GitHub](https://github.com/kepano/obsidian-skills) |
| 6 | Ego Lite | 使用浏览器访问网页、提取数据和完成操作 | [GitHub](https://github.com/citrolabs/ego-lite) |
| 7 | AI 简历助手 | 整理一页 A4 简历，输出 HTML/PDF | [GitHub](https://github.com/KevinYoung-Kw/vibe-resume-skill) |
| 8 | Kami 纸张 | 把 Markdown 排成正式文档和 PDF | [GitHub](https://github.com/tw93/kami) |
| 9 | WPS 操作 | 用自然语言操作 WPS 文字、表格和演示 | [GitHub](https://github.com/lc2panda/wps-skills) |
| 10 | Frontend Slides | 先预览风格，再生成网页幻灯片 | [GitHub](https://github.com/zarazhangrui/frontend-slides) |
| 11 | 归藏 PPT | 生成单文件 HTML 网页 PPT | [GitHub](https://github.com/op7418/guizang-ppt-skill) |
| 12 | Excalidraw 绘图 | 用自然语言生成可编辑图表 | [GitHub](https://github.com/coleam00/excalidraw-diagram-skill) |
| 13 | Bento | 单文件幻灯片编辑和演示 | [GitHub](https://github.com/nyblnet/bento) |
| 14 | HTML Anything | 75 种模板一键生成杂志、海报、社交卡片 | [GitHub](https://github.com/nexu-io/html-anything) |
| 15 | 女娲 Skill | 调用不同人物的思考框架分析问题 | [GitHub](https://github.com/alchaincyf/nuwa-skill) |

---

## 四、Codex 最值得推荐的 15 个 Skill

> 15 个中 7 个来自官方精选区，8 个从社区淘来。筛选标准就一条：**高频出现，装了确实比裸问 AI 靠谱**。

### （一）官方内置三件套（1–3）——「技能的技能」

先认识这三个，后面的技能才能装起来。它们都在官方技能目录 [openai/skills](https://github.com/openai/skills) 的 `.system` 里，随 Codex 自动装好，无需下载（同目录还有 imagegen 和 openai-docs）。OpenAI 没先建货架，先给了你生产工具——**技能这东西，攒比买重要**。

#### 1. skill-creator
创建技能的技能，每个 Agent 必备的原始技能。

#### 2. skill-installer
装技能的技能。先看看货架上有什么：

```
$skill-installer 看看有哪些技能
```

看中了哪个，一行命令进肚：`$skill-installer <技能名>`。

#### 3. plugin-creator
把自用技能打包成插件分享给团队。

### （二）开发流程八件套（4–11）

#### 4. create-plan（先规划后动手）
- **解决什么**：AI 上来就猛写、写完发现方向错了。
- **能力**：强制 Codex 在写第一行代码前产出实现计划。
- **来源**：社区精选仓库 [awesome-codex-skills](https://github.com/composio-community/awesome-codex-skills)（create-plan 子目录）

#### 5. grill-me（让 AI 反过来拷问你）
- **解决什么**：多数人用 AI 的短板不是 AI 不行，是需求没想清楚。
- **能力**：你提需求，它连环追问，每个分支聊清楚才放你走——把「想清楚」变成一场被迫完成的对话。
- **来源**：https://github.com/mattpocock/skills

#### 6. gh-fix-ci（CI 挂了别慌）— 官方精选
- **能力**：排查并修复 GitHub Actions 上失败的 PR 检查。每周因为流水线挂掉浪费的半小时，交给它。
- **安装**：`$skill-installer gh-fix-ci`

#### 7. gh-address-comments（PR 评论批量清）— 官方精选
- **能力**：处理当前分支 PR 上的 review 和 issue 评论，能改的直接改，要讨论的汇总成清单。审查意见十几条的 PR，一次清完。
- **安装**：`$skill-installer gh-address-comments`

#### 8. tdd（测试先行的老手艺）
- **能力**：红绿重构循环——先写失败的测试（红），写实现让它通过（绿），再重构。AI 猛写代码的冲动被测试摁住了。
- **来源**：同 grill-me（https://github.com/mattpocock/skills）

#### 9. diagnosing-bugs（纪律化调试）
- **解决什么**：AI 修 bug 最大的毛病是「猜一个原因改一版试试」。
- **能力**：定了纪律——先系统定位、收集证据，证据够了才动手。**tdd 管 bug 少生，它管 bug 生了怎么治。**
- **来源**：同 grill-me

#### 10. stop-slop（去 AI 腔）
- **能力**：清洗 AI 文本里的机翻味：delve、leverage、「此外」「值得注意的是」……README 和提交信息是重灾区。
- **来源**：https://github.com/hardikpandya/stop-slop

#### 11. sentry（线上炸了先看这里）— 官方精选
- **能力**：通过 Sentry CLI 只读查询 issue，把生产错误总结成人话。排障第一步的定位工具，已把服务上线的人值得装。
- **安装**：`$skill-installer sentry`

### （三）两个硬核补充（12–13）

#### 12. book-to-skill（把读过的书接进 Codex）
- **能力**：丢给它一本 PDF（你自己买的），拆成结构化技能：核心心智模型、每章一个文件、一份速查表。章节按需加载、问到才读，官方实测 token 消耗只有直接塞整本 PDF 的 **1/24 到 1/51**。
- **来源**：https://github.com/virgiliojr94/book-to-skill
- **安装**：`npx skills add virgiliojr94/book-to-skill`

#### 13. playwright（把浏览器交给 Codex 开）— 官方精选
- **能力**：从终端自动化真实浏览器——填表、截图、抓数据；前端改完让它真机验证，抓竞品页面数据也靠它。
- **安装**：`$skill-installer playwright`
- **增强版**：社区版 https://github.com/lackeyjb/playwright-skill ，带响应式检查和登录流程。

### （四）压轴的两个（14–15）

#### 14. cangjie-skill（仓颉技能，把书变成装备）
- **能力**：元技能——喂它一本书、一个长视频或播客的文字稿，它跑流水线把方法论拆成原子化能力卡，编译成可安装的技能包。你读完《穷查理宝典》记不住三条，它蒸馏出来的决策框架技能随时能被 Codex 调用。
- **与 book-to-skill 的区别**：book-to-skill 管读书查询，仓颉管**方法论上岗干活**。
- **来源**：https://github.com/kangarooking/cangjie-skill （9.2k 星，中文作者出品）

#### 15. last30days（压轴）
- **能力**：主清单里唯一不写代码的技能。给它一个话题或一个人，并行搜 Reddit、X、YouTube、Hacker News、Polymarket，按真实互动和真金白银的下注排序，合成一份带引用的简报。作者的话：**「Google 聚合的是编辑，last30days 搜索的是人。」**
- **来源**：https://github.com/mvanhorn/last30days-skill
- **安装**：`npx skills add mvanhorn/last30days-skill -g`

### Codex 15 技能速查表

| # | 技能 | 分类 | 一句话 | 来源 |
|---|---|---|---|---|
| 1 | skill-creator | 内置 | 创建技能的技能 | openai/skills（.system） |
| 2 | skill-installer | 内置 | 装技能的技能 | openai/skills（.system） |
| 3 | plugin-creator | 内置 | 把技能打包成插件分享团队 | openai/skills（.system） |
| 4 | create-plan | 开发流程 | 写代码前强制先出实现计划 | [awesome-codex-skills](https://github.com/composio-community/awesome-codex-skills) |
| 5 | grill-me | 开发流程 | AI 连环拷问，逼你想清需求 | [mattpocock/skills](https://github.com/mattpocock/skills) |
| 6 | gh-fix-ci | 开发流程 | 排查修复 GitHub Actions 失败 | 官方精选 `$skill-installer gh-fix-ci` |
| 7 | gh-address-comments | 开发流程 | PR 评论批量清 | 官方精选 `$skill-installer gh-address-comments` |
| 8 | tdd | 开发流程 | 红绿重构，测试先行 | [mattpocock/skills](https://github.com/mattpocock/skills) |
| 9 | diagnosing-bugs | 开发流程 | 先定位收集证据再动手修 | [mattpocock/skills](https://github.com/mattpocock/skills) |
| 10 | stop-slop | 开发流程 | 清洗 AI 腔（delve/leverage/此外…） | [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop) |
| 11 | sentry | 开发流程 | Sentry 生产错误总结成人话 | 官方精选 `$skill-installer sentry` |
| 12 | book-to-skill | 硬核补充 | 整本书拆成技能，token 省 24–51 倍 | [virgiliojr94/book-to-skill](https://github.com/virgiliojr94/book-to-skill) |
| 13 | playwright | 硬核补充 | 终端自动化真实浏览器 | 官方精选 `$skill-installer playwright` |
| 14 | cangjie-skill | 压轴 | 书/视频方法论蒸馏成技能包 | [kangarooking/cangjie-skill](https://github.com/kangarooking/cangjie-skill) |
| 15 | last30days | 压轴 | 近 30 天跨平台真实讨论简报 | [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) |

---

## 五、通用方法论：技能是可带走的资产

**SKILL.md 是通用标准**（[agentskills.io](http://agentskills.io)）：Claude Code、Codex、WorkBuddy、Cursor 认的是同一份文件。

实操就是复制粘贴：

```bash
# 同一份技能文件夹，两边各放一份
~/.claude/skills/my-tdd-skill/
~/.codex/skills/my-tdd-skill/

# 或者做个软链接，一处更新两边生效
ln -s ~/.codex/skills/my-tdd-skill ~/.claude/skills/my-tdd-skill
```

你在 Codex 里调教好的 `tdd`，Claude 那边零成本享用。

> **核心判断**：工具会一直换，但攒下来的技能库是自己的。
> - 逛市场的心态是「这平台有什么我用什么」；
> - 攒装备的心态是「我的东西跟着我走」。
>
> 早期生态乱一点没关系，**标准锁死了，资产就不会丢**。

---

## 六、上手路线建议

### Codex 玩家的推荐路径

1. **先跑通安装流程**：用内置三件套（skill-installer）熟悉技能机制；
2. **按日常挑三四个流程技能**（私心推荐 `create-plan` 和 `stop-slop`）；
3. **发布链三件套**：`gh-fix-ci` + `gh-address-comments` + `sentry`，凑成一条「CI 修复 → 评论清理 → 线上排障」的完整发布链；
4. **两个硬核补充看需求装**：读书多用 book-to-skill / cangjie-skill，前端活多用 playwright；
5. **last30days 记得带上**——不写代码但日常信息价值极高。

**最小行动**：打开终端，输入 `$skill-installer playwright`，五分钟后你就知道 Skill 是怎么回事了。

### WorkBuddy 玩家的推荐路径

1. **信息入口先装**：Deep Research + Last 30 Days，解决「搜什么、信什么」；
2. **知识沉淀跟上**：IMA 知识库或 Obsidian Skills（按你用的笔记软件二选一）；
3. **办公场景按需**：WPS 操作（日常办公）、AI 简历助手 / Kami（求职季）；
4. **表达输出进阶**：Frontend Slides / 归藏 PPT / Bento（网页幻灯片三选一）、HTML Anything（海报卡片）、Excalidraw（可编辑图表）；
5. **决策辅助彩蛋**：女娲 Skill，用名人心智模型分析具体问题。

---

## 七、注意事项与避坑

| # | 坑 | 说明与对策 |
|---|---|---|
| 1 | **技能装太多，判断失准** | 每个技能都会消耗模型上下文窗口；安装数量过多会导致模型选择技能时判断失准（大部分 Agent 工具都有此现象）。按需安装，不用的及时关掉。 |
| 2 | **装上≠生效** | Codex 装完问一句「你现在有哪些技能」，识别了才算装上。 |
| 3 | **Vibe Coding ≠ 听天由命** | AI 改完代码直接点确认不叫 Vibe Coding。要小步快跑：描述小功能 → 生成 → 运行测试 → 报错反馈再改，尽量看懂它的逻辑。 |
| 4 | **省的是敲代码时间，不是思考时间** | 给 AI「问题」而不只是「结果」：给谁用、解决什么、凭什么。需求描述的精度决定产出质量。 |
| 5 | **Demo 陷阱** | 从演示逻辑到真实产品要补六件事：接 CMS、接表单/支付、接数据、补边界（空态/错误提示）、查响应式、做性能优化。原型验证用 Vibe Coding 很爽，核心业务系统上生产前必须严谨。 |
| 6 | **代码能跑但不知道为什么能跑** | 安全、边界条件、错误处理 AI 不主动替你考虑；高风险系统（资金/隐私/核心业务）不适用「一句话生成」。 |
| 7 | **跨平台复用零成本** | SKILL.md 标准通用，技能文件夹复制或软链接即可在 Claude Code / Codex / WorkBuddy / Cursor 之间迁移。 |
