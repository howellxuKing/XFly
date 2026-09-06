<div align="center">
<img src="https://raw.githubusercontent.com/howellxuKing/x-panel-ui/main/public/logo.png" width="120" alt="X Panel" />
<h1>XFly</h1>
<p>XFly — X Panel 一键安装脚本（基于 Trojan Panel install-script 定制）</p>
</div>

## 支持系统

CentOS 7+ / Ubuntu 18+ / Debian 10+（x86_64 / arm64）

## 一键安装

```bash
source <(curl -L https://raw.githubusercontent.com/howellxuKing/xfly/main/install_script.sh)
```

按提示依次选择：

| 选项 | 功能 |
|---|---|
| **1** | 安装 X Panel 前端 UI（Nginx + 证书 + 伪装站） |
| **2** | 安装 X Panel 后端 API |
| **3** | 安装 X Panel Core（代理内核：Xray / Trojan-Go / Hysteria / Hysteria2 / NaiveProxy） |
| **8 / 9** | 更新 前端 / 后端 |
| **22** | 重置管理员密码 |

安装完成后访问 `https://你的域名:8888`，默认账号 `sysadmin`。

## 安装内容

- X Panel UI：`ghcr.io/howellxuking/x-panel-ui`
- X Panel Backend：`ghcr.io/howellxuking/x-panel`
- Core（内核）：`jonssonyan/trojan-panel-core`
- Nginx / Caddy2（证书 + 伪装） / MariaDB / Redis

> 版本检查机制：后端版本与脚本内置 `latest_version` 比对，不一致才会执行更新。改代码后请同步升级版本号，否则「更新后端」会提示已是最新。

## 客户端接入（Clash Verge）

订阅链接为 **Clash Verge** 量身定制，开箱即用：

1. **下载 Clash Verge**：<https://github.com/clash-verge-rev/clash-verge-rev/releases>（Windows 选 `x64-setup.exe`，国内下载慢可挂代理）
2. **复制订阅链接**：登录面板 → 个人中心 → 复制订阅地址
3. **一键订阅**：Clash Verge → 「订阅」→「新建」→ 粘贴链接 → 导入即用，无需任何手动配置（订阅自动更新，无外部规则文件下载）
4. **保持「规则模式」**（默认）：流量自动分流，国内直连、国外翻墙

**内置智能分流规则（全自动，零配置）：**

| 流量类型 | 走向 | 举例 |
|---|---|---|
| 🇨🇳 国内网站 / 电商 / 视频 | **直连 DIRECT** | 淘宝、京东、拼多多、抖音、B站、网易云、微信/QQ |
| 🤖 国外 AI / 开发者工具 | **代理 PROXY** | ChatGPT、Claude、Gemini、OpenAI、Google、GitHub |
| 🌍 其他国外流量 | **代理 PROXY** | YouTube、Telegram、X(Twitter)、流媒体等（兜底走代理） |

**效果：同一时间、同一个 Clash，AI 翻墙 + 国内电商带货/直播满速直连，互不干扰、无需来回切换。**

## 致谢

基于 [trojanpanel/install-script](https://github.com/trojanpanel/install-script) 定制，感谢原作者 jonssonyan 与社区。

## License

MIT
