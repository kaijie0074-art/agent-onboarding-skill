# Agent 上手教练（agent-onboarding）

> 一个装进 Claude Code / Codex 里的**交互式教程**：不是给你一篇文档读，而是 AI 化身"上手教练"，一步步牵着你把一个真实任务做完，并教会你下次自己怎么一句话搞定。面向零基础、尤其语音交互的用户。

---

## 📦 怎么安装（三选一）

### 方式一：一行命令（推荐，需要电脑装了 Node.js）
在终端运行：
```bash
npx skills add kaijie0074-art/agent-onboarding-skill -g
```
装完就能用，全局生效。

### 方式二：把活交给你的 AI（最省事，适合不想碰命令行的人）
把这个仓库地址发给你自己的 Claude Code / Codex，对它说：
> "帮我安装这个 skill 到 ~/.claude/skills/：https://github.com/kaijie0074-art/agent-onboarding-skill"

它会自己 clone 下来放好。

### 方式三：手动放文件
```bash
git clone https://github.com/kaijie0074-art/agent-onboarding-skill.git ~/.claude/skills/agent-onboarding
```
（或下载 zip 解压到 `~/.claude/skills/agent-onboarding/`）

> 可选：把仓库里的 `commands/上手.md` 拷到 `~/.claude/commands/`，就能用 `/上手` 命令直接启动。

---

## ▶️ 怎么用
安装后，对 Claude / Codex 说一句即可：
- **"带我上手"** / **"教我用 agent"** / **"我是新手，想做个微信群整理但不会"**
- 或用命令 **`/上手`**（也可 `/上手 文章转视频` 直接进某个项目）

教练会：选项目 → 自检环境（缺工具自动帮你装）→ **先用内置样例跑一遍**（1 分钟见效）→ 再用你自己的真实数据 → 做完告诉你"你只说了 X、Agent 做了 Y、以后你只要说这句话"。

---

## 覆盖 14 个项目（全部经真机实测）
**创业者**：① 微信群消息整理 ② 文章转短视频 ③ 飞书推送 ④ 自动回邮件 ⑤ 名片变官网 ⑥ 长文档总结 ⑦ 竞品监控 ⑧ 评论分析 ⑨ 行业简报 ⑩ 经营日报
**大学生**：A 自动作业 ／ B 个人网页(=⑤) ／ C 班级群整理(=①) ／ D 竞赛材料

## 目录结构
```
agent-onboarding/
├── SKILL.md          # 教练大脑：总流程 + 七条铁律 + 项目菜单
├── references/       # 12 份"带练剧本"，每个项目一份
├── assets/样例数据/   # 自带样例输入，"先用样例跑一遍"跨机器可用
└── commands/上手.md   # 可选的 /上手 中文命令
```

## 设计原则（写进了 SKILL.md，AI 会遵守）
一次只推进一步；能代做绝不让用户动手；每个选择给选项卡；先用样例给"小胜利"；诚实标 🟢/🟡/🔴 档位与可逆性；报错自己扛；做完必给教学闭环。

## 各项目可能用到的工具（缺了 AI 会按剧本引导你自动装，多数零准备）
微信整理 `@jackwener/wx-cli`｜文章转视频 `ffmpeg`+`Pillow`｜评论出图 `matplotlib`（中文字体防乱码）｜自动回邮件全自动版 `himalaya`（+邮箱开 IMAP/应用密码）｜飞书推送 群机器人 webhook 或 `@larksuite/cli`｜官网上线 `vercel`/`gh`/`cloudflared`｜竞品国内站 浏览器渲染(Playwright)｜竞赛出真 PPT `python-pptx`

## 许可
MIT。欢迎自由使用、修改、分发。
