<div align="center">
<img src="https://raw.githubusercontent.com/howellxuKing/x-panel-ui/main/public/logo.png" width="120" alt="X Panel" />
<h1>X Panel Install Script</h1>
<p>X Panel 一键安装脚本（基于 Trojan Panel install-script 定制）</p>
</div>

## 支持系统

CentOS 7+ / Ubuntu 18+ / Debian 10+（x86_64 / arm64）

## 一键安装

```bash
source <(curl -L https://raw.githubusercontent.com/howellxuKing/install-script/main/install_script.sh)
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

## 致谢

基于 [trojanpanel/install-script](https://github.com/trojanpanel/install-script) 定制，感谢原作者 jonssonyan 与社区。

## License

MIT
