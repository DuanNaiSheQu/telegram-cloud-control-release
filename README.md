<div align="center">

<h1>Telegram 云控</h1>

<p><b>面向自有账号与官方 Bot 的 Telegram 运维控制台</b><br>
在线状态 · 会话收件箱 · 任务队列 · Bot 转发 · 全链路审计</p>

<p>
  <a href="https://github.com/cafinxnull/telegram-cloud-control-release/releases"><img src="https://img.shields.io/badge/version-0.5.4-2AABEE.svg" alt="Version"></a>
  <a href="https://t.me/TGCloudcontrol"><img src="https://img.shields.io/badge/Telegram-%E4%BA%A4%E6%B5%81%E7%BE%A4-2AABEE?logo=telegram&logoColor=white" alt="Telegram 交流群"></a>
  <a href="https://github.com/sponsors/cafinxnull"><img src="https://img.shields.io/badge/Sponsor-%E8%B5%9E%E5%8A%A9-EA4AAA?logo=githubsponsors&logoColor=white" alt="赞助"></a>
</p>

</div>

---

## 这是什么

**Telegram 云控的「可试用发行版」** —— 前端界面 + 完整部署文档，**开箱即可看到真实界面**。

> ⚠️ **本仓库不包含后端服务。** 后端为核心商业部分，需**授权后提供**。
> 完整版获取方式见下方 [**获取完整版**](#获取完整版)。

## 包含 / 不包含

| | 内容 |
| --- | --- |
| ✅ **包含** | 前端编译产物（已压缩混淆）、完整部署文档、`docker-compose` 与 `.env` 样例、更新记录 |
| ❌ **不包含** | 后端 API、Worker（Telegram 账号调度与风控核心） |

**因此：把本包装起来后，界面能打开，但登录与数据需要连接一个后端服务。** 后端有两种获取方式 —— 见下。

## 快速开始

1. 取环境变量样例、按注释填写：

   ```bash
   cp deploy/.env.example deploy/.env
   ```

2. 按 [`docs/DEPLOYMENT.md`](docs/DEPLOYMENT.md) 部署；前端产物在 `web/`，交给 nginx 或任意静态服务托管即可；
3. 后端地址在 `.env` 里的 `VITE_API_BASE`（或部署时的反代规则）中指向你的后端实例。

## 获取完整版（含后端）

**后端不开源** —— 这套系统的价值集中在账号调度、节流与稳定性处理上，把这部分源码公开等于把工作成果直接送人。

需要**完整后端**、**二次开发**或**商业授权**，来 Telegram 交流群找我：

> **交流群：[t.me/TGCloudcontrol](https://t.me/TGCloudcontrol)**
>
> 进群说明来意（自用 / 商用 / 二次开发），我会按需求提供对应授权版本。

**授权范围**：自用部署不限账号数；商用与转售需单独洽谈。

## 部署前的必读事项

- **三个密钥上线必须替换**：`POSTGRES_PASSWORD` / `SECRET_KEY` / `SESSION_ENCRYPTION_KEY`。
  生成方式写在 `deploy/.env.example` 注释里。**密钥一旦有账号登录过就不能再改** —— 已入库的会话将解不开；
- **账号安全由部署者自行负责**：批量操作的频率上限、活跃时段、动作间隔请按自己的实际情况配置。
  系统内置了节流与熔断保护，但它**不是免死金牌**，任何自动化操作都有风险；
- **数据全部留在你自己的服务器上**，不经过任何第三方。

## 赞助支持

这个项目是持续维护的 —— 节流策略要跟着风控变化调整，Telegram 一改协议就得跟进。

如果它帮你省了时间、或者你希望它继续更新：

| 方式 | 入口 |
| --- | --- |
| **GitHub Sponsors** | [github.com/sponsors/cafinxnull](https://github.com/sponsors/cafinxnull) |
| **其他方式** | 到 [交流群](https://t.me/TGCloudcontrol) 找我 |

**赞助者的需求会优先处理**（提 issue、要功能、遇到问题都算）。

## 联系方式

| 渠道 | 地址 |
| --- | --- |
| **Telegram 交流群**（推荐） | [t.me/TGCloudcontrol](https://t.me/TGCloudcontrol) |
| **GitHub Issues** | [提交问题](https://github.com/cafinxnull/telegram-cloud-control-release/issues) |

**优先走交流群** —— issue 不常看，群里回得快。

## 许可

本发行版可自由用于**自己账号的运维**。

**禁止**：转售、去除赞助与出处标识、以本项目的衍生版本提供商业服务。

需要商业授权请通过上方联系方式洽谈。
