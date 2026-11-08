# DesignPilot — 零基础产品设计与开发向导

支持网页与微信小程序，从想法到视觉样稿、实现、验收和操作交付。它是指导编程助手工作的方法包，不是独立应用，也不自带生图、浏览器或微信开发者工具。

## 快速导航

- [详细使用教程](docs/使用教程.md)：第一次如何开始、怎样提供参考、每阶段会拿到什么。
- [安装与维护](docs/安装与维护.md)：Mac、Windows、项目安装、更新和卸载。
- [常见问题](docs/常见问题.md)：未识别 Skill、没素材、没有 AppID、验收工具不可用。
- [Skill 主入口](SKILL.md) · [行为测试场景](tests/scenarios.md)

## 适合谁

适合想做个人网站、品牌展示、预约服务或简单工具，但不熟悉设计与开发的用户。也适合已有项目、希望用参考图系统改进界面的人。

你不必先准备完整需求、设计稿或素材库。说清一个想法即可；助手会提出合理默认方案，并逐步收集真正影响下一步的信息。

## 安装

仓库名为 **designleader**，Skill 名仍为 **designpilot**，安装目录和调用命令都使用 `designpilot`。

已安装 Git 的用户可直接执行（Mac/Linux）：

```sh
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/linssenstudio/designleader.git "$HOME/.agents/skills/designpilot"
```

Windows PowerShell：

```powershell
git clone https://github.com/linssenstudio/designleader.git "$env:USERPROFILE\.agents\skills\designpilot"
```

目标目录已存在时不要强行覆盖，按[更新说明](docs/安装与维护.md)处理。没有 Git 可使用 [Download ZIP](https://github.com/linssenstudio/designleader/archive/refs/heads/main.zip)，解压后把 `designleader-main` 重命名为 `designpilot`。


解压后，将完整 `designpilot` 文件夹放到用户目录的 `.agents/skills/` 下。最终路径应为 `~/.agents/skills/designpilot/SKILL.md`，不要多套一层文件夹。这是当前 Codex 与 Kimi Code 文档共同支持的位置。Windows 对应用户目录如 `C:\Users\你的用户名\.agents\skills\designpilot`。

Mac/Linux：在解压后、能看到 designpilot 文件夹的目录打开终端，执行：

```sh
mkdir -p "$HOME/.agents/skills"
if [ -e "$HOME/.agents/skills/designpilot" ]; then
  echo '已有同名 Skill，请先备份或换名，不直接覆盖。'
else
  cp -R designpilot "$HOME/.agents/skills/designpilot"
fi
```

也可仅安装到 Git 项目根目录的 `.agents/skills/designpilot/`。只选一个位置，避免重复。重新打开助手会话；Codex 输入 `$designpilot`，Kimi Code 输入 `/skill:designpilot`。如果没有识别，检查目录层级、SKILL.md 大小写和客户端版本；可先让助手直接读取完整路径的 SKILL.md 使用。卸载只移走这个 Skill 文件夹，不影响已生成的项目。

## 直接这样用

Codex：
```
$designpilot 我想做一个摄影作品网站。我不会写代码，也没有参考，请给我默认方案，一步步带我完成。
```

Kimi Code：
```
/skill:designpilot 我想做一个微信预约小程序，没有设计素材。先做可体验的首版，不要真实支付。
```

已有项目：请用 DesignPilot 改进这个项目的界面，先分析现有截图和代码，保持现有功能。
恢复项目：请读取 designpilot-project/status.md，接着上次进度做，不要重新问已经确认过的问题。
自主模式：常规设计你决定，每阶段给我看成果；涉及真实发布或付费再按我的授权处理。

首次通常只会问“给谁做什么、在哪里用”。后续先看到简报与两套视觉小样，再选方向。你随时可以说“换个方向”“先不加动画”“我只想做本地演示”。文件保存在你的项目中，模板不会被覆盖。

## 包含内容

SKILL.md 为主入口；references/ 包含视觉参考、动效音效、工程路线、验收；templates/ 包含简报、设计素材规范、验收记录、交付指南与续接状态。无需安装额外 Skill 或 MCP 才能阅读和使用。

最低需要能读写项目文件的编程助手。运行代码需对应开发环境，视觉验收需浏览器/看图能力，小程序真机验收需微信开发者工具与手机。没有这些能力时仍可推进其他阶段，明确保留未验证项。

## 验证与边界

此包经过结构、相对引用和压缩包完整性检查；没有在 Kimi Code 与 Codex 各跑完整产品开发，不能声称双端行为已验证。tests/scenarios.md 提供后续真实会话验证用例。技术方案以任务约束为准，真实支付、平台审核和上线不由 Skill 保证。

安装依据（2026-11-08 查阅）：
- Codex：https://learn.chatgpt.com/docs/build-skills
- Kimi Code：https://www.kimi.com/code/docs/en/kimi-code-cli/customization/skills.html
