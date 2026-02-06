# SiteProxy - 定制版

这是基于 [netptop/siteproxy](https://github.com/netptop/siteproxy) 的定制版本。

## 主要修改

### 1. 简化首页 (`index_www.netptop.com.html`)

- ✅ 移除了 GitHub 和 Telegram 图标链接
- ✅ 移除了"新闻网站"板块（美国之音、纽约时报等）
- ✅ 移除了"海外论坛"板块（文学城、留园网等）
- ✅ 简化了页脚版权信息

### 2. 保留的功能

- ✅ 搜索引擎（Google IPv4/IPv6、DuckDuckGo、Bing）
- ✅ 常用网站（DuckDuckGo AI Chat、Wikipedia、YouTube、X/Twitter、APKMirror、Web Telegram）
- ✅ 深色/浅色主题切换
- ✅ 所有代理核心功能

## 部署说明

部署方式与原版 siteproxy 完全相同，请参考 [README.md](README.md) 中的部署指南。

### 快速部署到 VPS

```bash
# 1. 克隆仓库
git clone https://github.com/se-leife/siteproxy.git
cd siteproxy-custom

# 2. 安装依赖
npm install

# 3. 修改配置
nano config.json
# 设置 proxy_url 和 token_prefix

# 4. 启动服务
npm install -g forever
forever start bundle.cjs
```

### 快速部署到 Cloudflare Pages

```bash
# 1. 克隆仓库并安装依赖
git clone https://github.com/YOUR_USERNAME/siteproxy-custom.git
cd siteproxy-custom
npm install

# 2. 修改配置
nano wrangler.jsonc
# 设置 name, proxy_url, token_prefix

# 3. 登录并部署
npm run wrangler-login
npm run deploy-cf-page
```

## 配置示例

```json
{
  "proxy_url": "https://your-domain.com",
  "token_prefix": "/your-password/",
  "local_listen_port": 5006,
  "description": "token_prefix 相当于网站密码，请谨慎设置"
}
```

## 注意事项

- 本定制版移除了部分可能引起争议的内容板块
- 保留了所有核心代理功能
- 首页更加简洁，适合个人或团队使用

## 原项目

- 原项目地址：https://github.com/netptop/siteproxy
- 原作者：netptop
- 许可证：见 [LICENSE](LICENSE)

## 免责声明

本项目仅供学习交流使用，严禁用于任何非法用途。使用本项目所产生的一切后果由使用者自行承担。

## 更新日志

### 2025-02-06
- 基于 siteproxy 2.0 创建定制版
- 简化首页内容
- 移除敏感内容板块
