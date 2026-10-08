# Beidou-MS-Fix
针对北斗冒险岛的一些优化和修复/BeidouMS Fix

## 客户端

服务端与客户端均已打包，可在 [Release](https://github.com/deinthoedoka/Beidou-MS-Fix/releases/tag/fix-1.00) 页面下载。

## 本次修复2026.10.8（基于北斗1.12）
以后均为独立分支，不跟随北斗最新版本进行更新，只针对北斗issues和本issues中提到的bug进行修复

**技能与战斗**

- 圣骑士寒冰之剑 / 寒冰钝器现在可以冻结怪物（1 ~ 15 级 1 秒，16 ~ 30 级 2 秒）
- 修正多个冰冻技能的冻结时长翻倍问题
- 修复快速转职一转的时候能力值不返还的问题

**装备系统**

- 永恒 / 重生装备的升级后的技能词条现已生效 —— 恢复GMS083原版的等级（永恒6级，重生4级）

**怪物与地图**

- 修复低掉落倍率下组队任务道具不足
- 超级传送新增闹鬼宅邸外部地图

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

