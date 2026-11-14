---
name: download-sound-party-companion
description: 帮 Windows 11 x64 新手从 Sound Party Companion 的 GitHub Releases 获取安装包，校验 SHA256，并指导安装和启动。适用于下载这个 Xiaomi 蓝牙音箱 Pro 伴侣工具的请求。
---

# 下载并安装 Sound Party Companion

用简短的中文告诉用户要点哪个链接、如何确认下载完成，以及接下来在哪个界面操作。当前支持 Windows 11 x64。用户不清楚电脑类型时，指引查看“设置 → 系统 → 关于”里的 Windows 版本和“系统类型”，确认显示基于 x64 的处理器。

## 查找发布附件

1. 打开 [项目的 Latest Release](https://github.com/fang-123559/SoundPartyCompanion/releases/latest)。用户指定版本时，到同一仓库的 [Releases](https://github.com/fang-123559/SoundPartyCompanion/releases) 找对应的正式发布。
2. 在同一版本的 `Assets` 里选 `SoundPartyCompanion-Setup-<版本>-win-x64.exe` 和同名 `.exe.sha256` 文件。页面读不到附件列表时，查询 [GitHub Releases API](https://api.github.com/repos/fang-123559/SoundPartyCompanion/releases/latest)，从 `assets` 读取匹配附件的 `name` 和 `browser_download_url`。指定版本时用该 API 的 `/releases/tags/<tag>` 路径。根据实际附件给出版本和链接。`Source code (zip)`、打包报告和 GitHub Actions 产物跳过。
3. 当前环境无法联网核实新版时，可以提供下面已验证的 `v0.1.1` 备用链接，明确其版本。缺少匹配附件时，告诉用户缺的是哪一项。用户电脑打不开 GitHub 时，让用户提供浏览器报错，区分发布页打不开和文件下载失败。使用该项目 GitHub 发布附件作为下载来源。公开附件无需 GitHub 账号或网盘会员。

- [v0.1.1 发布页](https://github.com/fang-123559/SoundPartyCompanion/releases/tag/v0.1.1)
- [v0.1.1 Windows x64 安装包](https://github.com/fang-123559/SoundPartyCompanion/releases/download/v0.1.1/SoundPartyCompanion-Setup-0.1.1-win-x64.exe)
- [v0.1.1 SHA256 校验文件](https://github.com/fang-123559/SoundPartyCompanion/releases/download/v0.1.1/SoundPartyCompanion-Setup-0.1.1-win-x64.exe.sha256)

## 下载并校验

- 用户要求代下载且工具能写入用户的 Windows 电脑时，保存到用户指定的目录或浏览器默认下载位置。确认安装包实际下载完成，核对 SHA256 后报告保存路径和校验结果。
- 只能聊天、浏览网页或访问远程环境时，提供可点击的安装包和校验文件直链，指导用户在 Windows 电脑上打开，用 `Ctrl+J` 查看下载进度和文件位置。仅提供链接或在远程环境取得文件时，说明用户仍需在自己的电脑上下载。
- 用 PowerShell 的 `Get-FileHash -Algorithm SHA256 -LiteralPath "实际安装包路径"` 计算安装包哈希，与同版本 `.sha256` 文件开头的 64 个十六进制字符比较，忽略大小写。手动操作时，指导用户用记事本打开校验文件，在资源管理器中右击安装包并选择“复制文件地址”或“复制为路径”，再把路径填入命令，确保路径外只有一对双引号。
- 校验失败时停止安装指导，让用户回项目发布页重新下载并复验。若校验暂时无法完成，指出缺少的文件或步骤，说明当前状态是待校验。

## 指导用户安装

校验通过后，指导用户在 Windows 蓝牙设置中配对音箱并保持蓝牙开启，由用户亲自双击安装包、按向导操作，再从开始菜单打开 `Sound Party Companion`。`v0.1.1` 自带 .NET 运行库，按发布说明使用普通用户权限安装。用户遇到 Windows 拦截时，请其提供提示原文，按该版本的发布说明帮助判断。

### 双击安装包没有反应

1. 先确认用户双击的这份安装包来自项目的 GitHub 发布页，且 SHA256 与同版本校验文件一致。两项都确认后再继续。
2. 指导用户在资源管理器中右键点击这份安装包，打开“属性 → 常规”。如果窗口底部的“安全”提示右侧有“解除锁定”复选框，勾选它，点击“应用 → 确定”，再双击同一个文件。这一步只移除该文件的下载标记。若安装向导弹出，继续按向导安装。
3. 如果没有“解除锁定”选项，或重试后仍未弹出安装向导，指导用户打开“Windows 安全中心 → 病毒和威胁防护 → 保护历史记录”，查看与该安装包相关的记录。请用户提供 Windows 版本、重试结果和看到的提示原文。
