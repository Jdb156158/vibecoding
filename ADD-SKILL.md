# 新增技能 · 数据刷新流程

> 用途：后续发现新的好用 skill，按本流程加进指南，保证「网页 / Markdown 指南 / README」三处数字与卡片始终一致。
> 适用：WorkBuddy（W）或 Codex（C）任意平台新增一个技能。

---

## 一、改动清单（4 个文件）

| 文件 | 改什么 |
|---|---|
| `index.html` | ① SKILLS 数组追加 1 个卡片对象 ② 首页 `<b>总数</b>` 统计 ③ 目录/章节标题的「N 技能/N Skill」 |
| `vibecoding-guide.md` | ① 对应平台章节新增 `#### N.` 小节 ② 速查表新增 1 行 ③ 章节标题的数字、开头引用句的数字 |
| `README.md` | ① 章节表里的「平台 · N 技能」 ② 更新记录追加一行 |
| `ADD-SKILL.md` | 若新增了分类维度，补一句说明（通常不用动） |

> 数字规则：首页统计 = WorkBuddy 数 + Codex 数；目录/章节/速查表各自标注本平台数量。

---

## 二、index.html · 卡片对象写法

在 `<script>` 内的 `SKILLS` 数组末尾追加一条。字段说明：

```js
{p:W, cat:"分类名", no:"02", name:"技能名", cn:"中文别名",
 what:"解决什么（可用 <b>加粗</b>）",
 ex:"示例提示词",
 cmd:"安装命令", url:"https://github.com/...",
 badge:"官方精选",          // 可选：仅官方精选区技能加
 note:"补充说明"}            // 可选：星标/社区增强版等
```

- `p`：`W` = WorkBuddy，`C` = Codex
- `cat`：分组标题，会直接显示为网页里的分组标签。**新增「节省 token」类技能就填 `cat:"节省token的skill"`**；想新增别的主题分组，直接起新名字即可（渲染会自动按出现顺序建分组）
- `no`：本平台序号，两位数补零（如 `"02"`、`"16"`）
- `cmd`：WorkBuddy 用自然语言安装句式，Codex 用 `$skill-installer xxx` 或 `npx skills add ...`

刷新后务必同步：
1. 首页 `<div class="stat"><b>31</b><span>精选技能</span></div>` 的 `31` → 新总数
2. 目录 `<a href="#s4">…Codex · 16 Skill</a>` 与章节 `<h2>Codex · 16 Skill</h2>` 的数字
3. 章节引导语 `16 个中 7 个来自官方精选区…` 的人数拆分

---

## 三、vibecoding-guide.md · 写法

1. **章节标题**：`## 四、Codex 最值得推荐的 16 个 Skill` 同步数字
2. **开头引用句**：`> 16 个中 7 个来自官方精选区，8 个从社区淘来…` 同步拆分
3. **新增小节**：在对应分组下加
   ```md
   #### 16. andrej-karpathy-skills（节省 token 的行为指南）
   - **能力**：……
   - **示例**：……
   - **安装**：`命令`
   - **来源**：https://github.com/...
   ```
4. **速查表**：在 `### Codex 16 技能速查表` 末尾加一行
   `| 16 | 技能名 | 分类 | 一句话 | [仓库](url) |`

---

## 四、校验与提交（本仓库特有坑）

```bash
cd "/Volumes/My Passport/100App/GitHub/vibecoding"

# 1) 校验网页 JS 语法（提取 <script> 用 node 检查）
python3 - <<'EOF'
import re
html = open("index.html", encoding="utf-8").read()
m = re.search(r"<script>(.*?)</script>", html, re.S)
open("/tmp/vb_check.js","w",encoding="utf-8").write(m.group(1))
EOF
node --check /tmp/vb_check.js && echo "JS OK"

# 2) 外置盘 AppleDouble 污染清理（否则 git 报 non-monotonic index）
find .git -name "._*" -delete

# 3) 提交
git add index.html vibecoding-guide.md README.md
git commit -m "feat: 新增 <技能名> 技能，刷新统计至 <总数>"

# 4) 推送（本地代理偶发瞬断，失败就直连重试）
git push origin main \
  || env -u HTTP_PROXY -u HTTPS_PROXY -u http_proxy -u https_proxy git push origin main
```

---

## 五、上线验证

GitHub Pages 每次 push 到 `main` 自动重新部署（约 1 分钟）：

```bash
sleep 45
curl -s -o /dev/null -w "live HTTP %{http_code}\n" -L "https://jdb156158.github.io/vibecoding/"
# 抽查关键词是否出现
curl -s -L "https://jdb156158.github.io/vibecoding/" | grep -c "技能名"
```

确认返回 200 且新技能卡片可见即可。

---

## 六、约定速记

- 总数 = WB + Codex，首页只改这一处统计
- 平台标题/目录/章节/速查表各自标注本平台数量
- 「节省 token 类」统一归到 `cat:"节省token的skill"` 分组，置于官方技能之后
- 来源、作者信息一律不写进仓库
