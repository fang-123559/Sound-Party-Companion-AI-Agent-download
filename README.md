# Sound Party Companion 豆包下载助手

帮第一次使用 GitHub 的用户下载 Sound Party Companion 的 Windows 11 x64 安装包。两种方式都从原项目的 GitHub Releases 获取安装包，并提供 SHA256 校验、安装和启动排查步骤。

## 豆包对话

打开[豆包提示词](./download-with-ai.txt)，复制全文并发送给豆包。按它给出的链接和步骤在 Windows 电脑上下载。

## 豆包工作

1. 下载 [Skill ZIP](https://github.com/fang-123559/SoundPartyCompanion-Doubao/releases/latest/download/download-sound-party-companion.zip)，把 ZIP 原文件上传到豆包工作。
2. 随附件发送下面这句话。

> 请从我上传的 ZIP 中导入并安装到项目级，同时启用 download-sound-party-companion 技能，帮我从 GitHub 下载最新版 Sound Party Companion 的 Windows 11 x64 安装包，核对 SHA256，并一步步指导我安装。

可以直接查看 [SKILL.md](./download-sound-party-companion/SKILL.md)。

## 实测反馈

- ✅ **豆包对话（P3）**：发送提示词后，豆包给出了 `v0.1.1` 的 Windows x64 安装包和 SHA256 校验文件的 GitHub 直链。
- ✅ **豆包工作（P1–P2）**：导入 Skill 后，在 Windows 11 x64 上下载了 `v0.1.1` 安装包（56,202,850 字节）和校验文件。实测 SHA256 与项目发布值一致，资源管理器中也能看到下载的文件。

本次反馈验证到下载与 SHA256 校验，安装和启动结果待确认。

原项目与安装包发布页见 [Sound Party Companion](https://github.com/fang-123559/SoundPartyCompanion) 和 [Windows 安装包 Releases](https://github.com/fang-123559/SoundPartyCompanion/releases/latest)。
