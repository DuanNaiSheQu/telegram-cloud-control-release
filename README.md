<div align="center">

<img src="docs/assets/logo.png" width="132" alt="TGcloud">

<h1>Telegram 云控 · 预编译部署包</h1>

<p><b>面向自有账号与官方 Bot 的 Telegram 运维控制台</b><br>
在线状态 · 会话收件箱 · 任务队列 · Bot 转发 · 全链路审计</p>

<p>
  <a href="https://github.com/DuanNaiSheQu/telegram-cloud-control"><img src="https://img.shields.io/badge/%E6%BA%90%E7%A0%81%E4%BB%93%E5%BA%93-DuanNaiSheQu%2Ftelegram--cloud--control-2AABEE?logo=github" alt="源码仓库"></a>
  <a href="https://github.com/DuanNaiSheQu/telegram-cloud-control/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License"></a>
  <a href="https://t.me/TGCloudcontrol"><img src="https://img.shields.io/badge/Telegram-%E4%BA%A4%E6%B5%81%E7%BE%A4-2AABEE?logo=telegram&logoColor=white" alt="Telegram 交流群"></a>
  <a href="https://github.com/sponsors/DuanNaiSheQu"><img src="https://img.shields.io/badge/Sponsor-%E8%B5%9E%E5%8A%A9-EA4AAA?logo=githubsponsors&logoColor=white" alt="赞助"></a>
</p>

<p>
  <img src="https://img.shields.io/badge/python-3.12-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/node-%E2%89%A520-339933?logo=nodedotjs&logoColor=white" alt="Node">
  <img src="https://img.shields.io/badge/postgresql-16-4169E1?logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/redis-7-DC382D?logo=redis&logoColor=white" alt="Redis">
  <img src="https://img.shields.io/badge/status-%E5%8F%AF%E7%94%A8-3fb950" alt="Status">
</p>

<p><b>本项目已完整开源（含后端）</b></p>

</div>

<div align="center">

### 赞助商

<table>
  <tr>
    <td align="center" width="50%">
      <a href="https://cafinx.com"><img src="docs/assets/sponsor/cafinx.png" width="178" alt="CAFINX 虚拟卡"></a><br>
      <b><a href="https://cafinx.com">CAFINX 虚拟卡</a></b><br>
      <sub>跨境收付虚拟卡 · cafinx.com</sub>
    </td>
    <td align="center" width="50%">
      <a href="https://cafinxsim.com"><img src="docs/assets/sponsor/cafinxsim.png" width="200" alt="CAFINXSIM"></a><br>
      <b><a href="https://cafinxsim.com">CAFINXSIM</a></b><br>
      <sub>全球 eSIM 流量卡 · cafinxsim.com</sub>
    </td>
  </tr>
</table>

</div>

---

## 这个仓库是什么

**完整源码在这里** 👉 **[DuanNaiSheQu/telegram-cloud-control](https://github.com/DuanNaiSheQu/telegram-cloud-control)**

本仓库是它的**预编译部署包** —— 前端已经构建好，**不需要装 Node / 跑 `npm build`**。

| | 本仓库（预编译包） | [源码仓库](https://github.com/DuanNaiSheQu/telegram-cloud-control) |
| --- | --- | --- |
| **前端产物** | ✅ 已编译（`web/`，直接托管） | 需自行 `npm run build` |
| **后端源码** | ❌ 不含 | ✅ 完整 |
| **部署文档** | ✅ `docs/` | ✅ `docs/` |
| **适合谁** | 想**最快跑起来**、不想配构建环境 | 想**读实现 / 改造 / 参与开发** |

**要改代码、要看实现、要提 PR —— 去源码仓库。想直接部署用 —— 留在这里就行。**

## 目录

```
web/        前端编译产物（已压缩混淆，交给 nginx 即可）
docs/       部署文档：快速开始 / 部署 / Linux 环境验证 / 功能 / 安全
deploy/     环境变量样例、部署配置
```

## 快速开始

```bash
# 1. 环境变量：按注释填写，三个密钥上线必须替换
cp deploy/.env.example deploy/.env

# 2. 前端产物在 web/，用 nginx 或任意静态服务托管
#    后端地址在 .env 的 VITE_API_BASE（或反代规则）里指向你的后端实例

# 3. 后端：从源码仓库克隆并启动
git clone https://github.com/DuanNaiSheQu/telegram-cloud-control.git
```

- **先跑起来** → [GETTING_STARTED.md](docs/GETTING_STARTED.md)
- **正式上线** → [DEPLOYMENT.md](docs/DEPLOYMENT.md)
- **Linux 服务器** → [LINUX_VERIFY.md](docs/LINUX_VERIFY.md)（**部署前必看**）

## 部署前必读

- **三个密钥上线必须替换**：`POSTGRES_PASSWORD` / `SECRET_KEY` / `SESSION_ENCRYPTION_KEY`。
  **密钥一旦有账号登录过就不能再改** —— 已入库的会话将解不开；
- **账号安全由部署者自行负责**：批量操作的频率上限、活跃时段、动作间隔请按实际情况配置。
  系统内置节流与熔断保护，但它**不是免死金牌** —— **任何自动化操作都有被平台限制的风险**；
- **数据全部留在你自己的服务器上**，不经过任何第三方。

<div align="center">

### 支持这个项目

<a href="https://github.com/sponsors/DuanNaiSheQu"><img src="https://img.shields.io/badge/Sponsor-%E8%B5%9E%E5%8A%A9-EA4AAA?logo=githubsponsors&logoColor=white" alt="Sponsor"></a>
<a href="https://t.me/TGCloudcontrol"><img src="https://img.shields.io/badge/Telegram-%E4%BA%A4%E6%B5%81%E7%BE%A4-2AABEE?logo=telegram&logoColor=white" alt="Telegram 交流群"></a>

**USDT（TRC20）**：`TYozr2b8tV4fikCuQYYvaHRCW555555555`　⚠️ 必须走 TRC20 网络

如果这套系统帮你省下了时间，欢迎赞助支持持续维护 —— **赞助者的需求优先处理**。

</div>

---

## 文档

| 文档 | 内容 |
| --- | --- |
| [文档索引](docs/README.md) | 按用途分类 |
| [快速开始](docs/GETTING_STARTED.md) | 从产物到看见界面 |
| [部署](docs/DEPLOYMENT.md) | 正式部署与上线清单 |
| [Linux 环境验证](docs/LINUX_VERIFY.md) | 服务器部署必看 |
| [架构概览](docs/ARCHITECTURE.md) | 系统组成与数据流 |
| [功能清单](docs/FEATURES.md) | 完整功能列表 |
| [安全说明](docs/SECURITY.md) | 密钥管理与数据存放 |
| [更新记录](CHANGELOG.md) | 每个版本改了什么 |

## 开源声明

本项目为开源项目，代码仅供学习研究用途。开源不易，请使用者尊重开发者的劳动成果。

### ⚠️ 重要提醒：请务必合法使用本项目

1. **合法合规**：使用者承诺仅在符合所在国家、地区法律法规，以及 Telegram 平台用户协议的前提下使用本项目；
2. **禁止用途**：禁止将本项目用于**非法入侵、批量骚扰、违规群发、未经许可的数据爬取、恶意群控**以及其他任何违法违规场景；
3. **风险自担**：本软件按「现状」提供，不提供任何明示或暗示担保。因使用者违规部署、不当使用项目而产生的一切风险、责任、损失，均由**使用者本人自行承担**，项目作者不承担任何法律及连带责任；
4. **二次分发**：如果进行二次修改、分发，需要遵守项目对应的开源许可协议，**保留原项目开源声明与版权信息，不得去除原作者标识**；
5. **平台规则**：严禁用于破坏平台规则、侵犯他人隐私与权益的行为，若用于违规用途，请立即停止使用。

### 💡 建议

仅用于个人学习、私人授权环境内测试；使用前请充分读懂代码逻辑，评估安全风险；
**请勿直接公网裸奔部署**。如发现他人利用本项目进行违法活动，请及时制止或举报。

## 许可

**MIT** —— 完整条款见 [源码仓库的 LICENSE](https://github.com/DuanNaiSheQu/telegram-cloud-control/blob/main/LICENSE)。

> 本项目仅用于管理**你自己拥有或有权操作**的账号与 Bot。请遵守 Telegram 服务条款与所在地区法律，**使用风险由部署者自行承担**。
