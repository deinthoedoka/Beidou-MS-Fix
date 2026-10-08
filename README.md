# Beidou-MS-Fix
针对北斗冒险岛的一些优化和修复/BeidouMS Fix
## 简介

北斗是一个开源的冒险岛私服服务端，专注于**中文本地化**与**游戏体验优化**。

技术血统：OdinMS → HeavenMS → Cosmic → 北斗。

---

## 主要特性

- **同进程双引擎** —— Spring Boot 提供管理后台与 REST API，Netty 承载游戏服，一体启动
- **数据库自动初始化** —— 首次启动自动建库并执行迁移脚本，只需保证 MySQL 已运行
- **Web 管理后台** —— 内置 Vue 3 管理界面，可在线控制游戏服启停、查看在线、管理账号
- **双语数据覆盖** —— 英文基础数据 + 中文覆盖层，中英文客户端共用一套服务端
- **动态游戏配置** —— 经验、掉落、金币等运营参数可在后台热重载，无需重启
- **全量中文** —— 客户端文本汉化率 **98.6%**，技能、任务、地图、NPC、道具全部中文化

---

## 技术栈

| 组件 | 技术 |
|---|---|
| 服务端 | Java 21 · Spring Boot 3 · Netty |
| 管理后台 | Vue 3 · Vite · TypeScript · Arco Design |
| 数据库 | MySQL 8+ · MyBatis-Flex · Flyway |
| 脚本引擎 | GraalVM JS |

---

## 快速开始

### 环境要求

- JDK 21
- MySQL 8 或更高版本
- Maven 3.9+

### 构建

```bash
mvn clean package
```

产物：`gms-server/target/BeiDou.jar`

### 运行

```bash
java -jar gms-server/target/BeiDou.jar
```

也可使用 `gms-server/launch.bat`（Windows）或 `launch.sh`（Linux）。

默认数据库连接：`localhost:3306/beidou`，账号 `root` / `root`。**首次启动会自动建库并执行初始化脚本。**

### 端口

| 用途 | 端口 |
|---|---|
| 登录 | 8484 |
| 游戏频道 | 7575 ~ 7577 |
| 管理后台 / API | 8686 |

### 管理后台

```bash
cd gms-ui
yarn install
yarn dev        # 开发模式，端口 8787
yarn build      # 生产构建，产物拷入服务端 static 目录，同源发布
```

---

## 客户端

服务端与客户端均已打包，可在 [Release](https://github.com/deinthoedoka/Beidou-MS-Fix/releases/tag/fix-1.00) 页面下载。

---

## 本次更新2026.10.8（基于1.12）
以后均为独立分支，不跟随北斗最新版本进行更新，只针对北斗issues和本issues中提到的bug进行修复

修复 **8 项问题**、补全 **1 项功能**、修正 **4 类数据**，并完成客户端全量汉化：

**技能与战斗**

- 圣骑士寒冰之剑 / 寒冰钝器现在可以冻结怪物（1 ~ 15 级 1 秒，16 ~ 30 级 2 秒）
- 修正多个冰冻技能的冻结时长翻倍问题

**装备系统**

- 永恒 / 重生装备的升级后的技能词条现已生效 —— 恢复GMS083原版的等级（永恒6级，重生4级）

**怪物与地图**

- 修复低掉落倍率下组队任务道具不足

**后台管理**

- 修复 Web 后台商城部分商品显示异常
- 修复 Web 后台刷新页面掉登录

**客户端汉化**

- 文本汉化率 **87.2% → 98.6%**，写入 12,417 条译文
- **2,842 个任务 100% 中文化**
- 544 条商城礼包名称汉化

---

## 致谢

- [Cosmic](https://github.com/P0nk/Cosmic) —— 本项目的直接基础
- [BeiDouMS](https://github.com/BeiDouMS/BeiDou-Server) —— 本项目的二次开发
- [HeavenMS](https://github.com/ronancpl/HeavenMS) —— Cosmic 的前身
- [maplestory.io](https://maplestory.io) —— 管理后台的图片接口

---

## 许可

本项目基于 **AGPL-3.0** 发布，详见 [LICENSE](LICENSE)。
