# FurAffinity App

[English](README.md) · **中文**

面向 [FurAffinity](https://www.furaffinity.net/) 的非官方 [Flutter](https://flutter.dev/) 第三方客户端。浏览作品、管理登录会话、搜索站点、查看用户资料，并提供移动端界面与可选的 LLM 翻译。

> **免责声明：** 本项目与 FurAffinity 及其运营方**无任何关联、背书或授权关系**。本应用仅代表你访问其公开网站，使用风险自负，并须遵守 [FurAffinity 服务条款](https://www.furaffinity.net/tos/)。

## 下载

**Android**（APK）— 安装到手机后，若系统提示，请允许「未知来源」安装。

| 版本 | 下载 |
|------|------|
| **最新版** | [Releases](https://github.com/Rehtt/furaffinity_app/releases/latest) |
| **v1.1.1** | [furaffinity_app-1.1.1.apk](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.1/furaffinity_app-1.1.1.apk) · [SHA256](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.1/furaffinity_app-1.1.1.apk.sha256) · [发布说明](https://github.com/Rehtt/furaffinity_app/releases/tag/v1.1.1) |
| **v1.1.0** | [furaffinity_app-1.1.0.apk](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.0/furaffinity_app-1.1.0.apk) · [SHA256](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.0/furaffinity_app-1.1.0.apk.sha256) · [发布说明](https://github.com/Rehtt/furaffinity_app/releases/tag/v1.1.0) |
| **v1.0.0** | [furaffinity_app-1.0.0.apk](https://github.com/Rehtt/furaffinity_app/releases/download/v1.0.0/furaffinity_app-1.0.0.apk) · [发布说明](https://github.com/Rehtt/furaffinity_app/releases/tag/v1.0.0) |

安装包见 [Releases](https://github.com/Rehtt/furaffinity_app/releases) 页面。

## 版本日志

### v1.1.1 — 2026-05-25

围绕配置迁移、FurAffinity 内链跳转和认证图片加载修复的发版。

- 新增应用配置备份与恢复，支持 JSON 文件或字符串导出导入
- 新增 FurAffinity 链接解析，可在应用内跳转用户、作品、合集与搜索页面
- 外部链接改用浏览器打开，不支持的 FA 页面使用应用内 WebView 兜底
- 首页新增 URL 跳转入口，可打开粘贴的 FurAffinity 链接

### v1.1.0 — 2026-05-25

围绕标签翻译、个人资料体验和 Android 发版打包的体验改进版本。

- 新增本地标签翻译字典，支持管理词条、JSON 导入 / 导出，以及通过 URL 导入
- 新增作品标签工具，可保存翻译、翻译选中标签、复制已翻译标签
- 打开 FA 标签搜索时会为多词标签关键词自动加引号
- 关于页面新增 GitHub 项目链接
- 浏览自己的个人资料时隐藏关注按钮
- Android 包名更新为 `com.rehtt.furaffinity_app`
- 发版构建现在会发布已签名 APK 和 SHA256 校验文件

### v1.0.0 — 2026-05-24

首个公开发布的 Android 版本。

- 首页动态：瀑布流、下拉刷新、分页
- 登录：应用内 WebView 或粘贴 Cookie（`flutter_secure_storage` 本地存储）
- 作品详情：信息 / 标签 / 评论、全屏缩放、列表滑动浏览、下载、收藏
- 用户主页：主页、画廊、废稿、收藏、关注与粉丝
- 高级搜索（FA 选项）与页内结果
- 本地浏览历史
- Cloudflare 人机验证流程
- 设置：主题、中/英文、网格列数、预览画质、图片缓存
- 可选：兼容 OpenAI 的翻译 API

## 功能

- **首页动态** — 首页最新缩略图瀑布流，支持下拉刷新与分页加载。
- **登录** — 应用内 WebView 登录，或粘贴会话 Cookie；凭据通过 [flutter_secure_storage](https://pub.dev/packages/flutter_secure_storage) 本地安全存储。
- **作品详情** — 信息 / 标签 / 评论分页；全屏双指缩放；从列表进入时可左右滑动浏览；支持下载；登录后可收藏 / 取消收藏。
- **用户主页** — 主页、画廊、废稿、收藏、关注与粉丝列表。
- **搜索** — 支持 FA 高级搜索（排序、分级、类型、时间范围、关键词模式等），结果页内展示。
- **浏览历史** — 本地记录已浏览作品，可在应用内清空。
- **Cloudflare 验证** — 站点要求人机验证时提供专门流程，验证通过后再加载图片。
- **设置** — 跟随系统 / 浅色 / 深色主题；中/英文界面（或跟随系统）；网格列数；作品预览画质（@300 / @600 / @1200 / 原图）；内存图片缓存管理。
- **可选翻译** — 兼容 OpenAI 的 API，自行配置 Base URL、API Key 与模型后翻译作品文本。

## 支持平台

| 平台 | 状态 |
|------|------|
| **Android** | 已支持 |
| iOS / 桌面 / Web | 暂未提供 |

## 使用说明

### 登录

1. 打开侧栏，点击**登录**，在 WebView 中完成登录；或  
2. 在**设置 → 账户 Cookie** 中粘贴有效的 `name=value; …` 字符串并保存（保存前会校验会话）。

退出登录会清除已保存的会话 Cookie。

### 翻译（可选）

进入**设置 → 翻译设置**，配置兼容 OpenAI 的 API 地址、密钥、模型与系统提示词。仅在你主动点击翻译时才会请求；未配置第三方端点时不会外发数据。

## 法律与商标

- **FurAffinity** 及相关标识归其权利人所有。本仓库仅在说明兼容性时使用该名称。
- 你须自行遵守 FurAffinity 条款、适用法律与内容政策。维护者按**原样**提供本软件，不作任何担保。

## 许可证

[MIT](LICENSE) © 2026 Rehtt
