# 隐私安全工具合集

> 保护你的数字隐私 | DNS加密 | 广告拦截 | 浏览器隐私设置 | 翻墙隐私保护指南

[![Stars](https://img.shields.io/github/stars/flclash-us/privacy-security-tools?style=flat)](https://github.com/flclash-us/privacy-security-tools)
[![License](https://img.shields.io/badge/License-MIT-blue)](LICENSE)

---

## 📋 目录

- [DNS 加密](#dns-加密)
- [广告拦截](#广告拦截)
- [浏览器隐私](#浏览器隐私)
- [密码管理](#密码管理)
- [翻墙隐私](#翻墙隐私)
- [通讯加密](#通讯加密)

---

## 🔐 DNS 加密

### 推荐的加密 DNS 服务

| 服务商 | 协议 | 特点 | 地址 |
|--------|------|------|------|
| Cloudflare | DoH/DoT | 速度快，隐私好 | 1.1.1.1 |
| Quad9 | DoH/DoT | 安全过滤 | 9.9.9.9 |
| AdGuard | DoH | 内置广告拦截 | dns.adguard.com |

### Clash DNS 配置

```yaml
dns:
  enable: true
  listen: 0.0.0.0:53
  enhanced-mode: fake-ip
  nameserver:
    - https://1.1.1.1/dns-query
    - https://8.8.8.8/dns-query
  fallback:
    - https://dns.google/dns-query
    - https://cloudflare-dns.com/dns-query
```

---

## 🛡️ 广告拦截

### 推荐工具

| 工具 | 平台 | 类型 | 链接 |
|------|------|------|------|
| AdGuard | 全平台 | 软件 | adguard.com |
| uBlock Origin | 浏览器 | 插件 | 开源免费 |
| Pi-hole | 路由器 | DNS级 | 开源免费 |

### Clash 广告拦截规则

```yaml
rule-providers:
  reject:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/reject.txt"
    path: ./ruleset/reject.yaml

rules:
  - RULE-SET,reject,🛑 广告拦截
```

---

## 🌐 浏览器隐私

### 推荐浏览器

| 浏览器 | 特点 | 适用场景 |
|--------|------|----------|
| Firefox | 开源，隐私好 | 日常使用 |
| Brave | 自带广告拦截 | 隐私浏览 |
| Tor Browser | 匿名网络 | 高隐私需求 |

### 浏览器隐私设置清单

- [ ] 禁用第三方 Cookie
- [ ] 启用 Do Not Track
- [ ] 禁用地理位置
- [ ] 清除浏览数据（定期）
- [ ] 使用隐私搜索引擎（DuckDuckGo）

---

## 🔑 密码管理

### 推荐工具

| 工具 | 开源 | 特点 |
|------|:----:|------|
| Bitwarden | ✅ | 免费版够用，自托管 |
| KeePassXC | ✅ | 本地存储，完全免费 |
| 1Password | ❌ | 用户体验好，付费 |

---

## 🕵️ 翻墙隐私

### 使用 VPN/代理时的隐私建议

1. **选择可信服务商**
   - 查看隐私政策
   - 选择无日志政策
   - 避免免费 VPN

2. **使用 Kill Switch**
   - 防止 VPN 断开时泄露真实 IP
   - Clash/Clash Verge 支持

3. **分离身份**
   - 翻墙账号与真实身份分离
   - 使用专用邮箱注册

4. **DNS 防泄露**
   - 使用加密 DNS
   - 在 Clash 中启用 DNS 劫持

### Clash 隐私配置

```yaml
# 防止 DNS 泄露
dns:
  enable: true
  enhanced-mode: fake-ip
  fake-ip-range: 198.18.0.1/16
  
# 使用加密 DNS
  nameserver:
    - https://1.1.1.1/dns-query
    - https://dns.google/dns-query
```

---

## 💬 通讯加密

### 推荐工具

| 工具 | 加密 | 开源 | 特点 |
|------|:----:|:----:|------|
| Signal | ✅ | ✅ | 最安全的即时通讯 |
| Telegram | ✅ | 部分 | 功能丰富，Secret Chat |
| ProtonMail | ✅ | 部分 | 加密邮箱 |

---

## 🔗 相关资源

| 资源 | 链接 |
|------|------|
| Clash for Windows | [clashforwindows.site](https://clashforwindows.site) |
| Clash 资源站 | [flclash.us](https://flclash.us) |
| Android 教程 | [clashmi.site](https://clashmi.site) |
| PrivacyTools | [privacytools.io](https://www.privacytools.io) |

---

<p align="center">
  保护隐私，从每一个细节开始 🔒
</p>