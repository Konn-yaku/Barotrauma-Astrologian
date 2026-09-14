# Astrologian 占星术士

《潜渊症》(Barotrauma) 的职业模组。加入一个以《最终幻想14》**占星术士**（Astrologian）为主题的治疗职业，
定位与数值基线取自原版**医生**（Medical Doctor）。

> **开发中 (WIP)** — 三条专精线中已完成一条，其余内容见下方「完成度」表。

## 特点

- **治疗者定位** — 主技能为医疗，不擅长战斗，更偏向艇内支援
- **纯 XML 实现** — 不依赖 Lua / LuaCsForBarotrauma，无需任何脚本前置
- **中英双语** — 简体中文与英文文本齐全
- **原创天赋** — 不是原版天赋的换皮，每个天赋都按潜渊症真实的治疗逻辑设计
- **与「天赋增强」风格一致** — 专精不互斥、解锁门槛与其保持一致

## 完成度

| 内容 | 状态 |
|---|---|
| 职业本体（技能 / 初始装备 / AI 行为 / 指令） | ✅ 完成 |
| 专精线一 · 治疗（5 个原创天赋） | ✅ 完成，已在游戏中验证 |
| 专精线二 · 群体增益（奥秘卡 / 抽卡） | 🚧 设计中 |
| 专精线三 | 🚧 待定 |
| 初级天赋 | 🚧 暂为占位内容 |
| 专属装备与职业图标 | 🚧 计划中 |

## 治疗线内容

| 层 | 天赋 | 效果 |
|---|---|---|
| 1 | **天星交错** | 医疗技能 +30；被治疗的队友获得 15% 全伤害抗性，持续整个任务 |
| 2 | **先天禀赋** | 目标生命值低于 30% 时，你的治疗效果提升至 2.2 倍 |
| 2 | **光速** | 潜艇上有人失去知觉时，你获得 30% 移动速度加成；心肺复苏效力提升 |
| 3 | **阳星合相** | 你在潜艇内时，1000 范围内的船员持续缓慢自愈（不断减轻伤害与出血） |
| 4 | **星天开门** | 进入任务时全船各获得一张庇护；各自倒地时自动触发，恢复满血后消耗。每名船员每次任务各自可触发一次 |

## 设计说明

潜渊症**没有"回血"这个概念**。角色身上挂着各种状态（affliction），
医生的工作是**削减它们**——绷带只治出血、血袋只治失血、抗生素只治感染，用错药完全无效。

因此本模组的天赋不是"提高治疗量"，而是围绕这几件事设计：

- 让药物更有效、持续时间更长
- 减少药物消耗、自动处理状态
- 打断「出血 → 失血 → 伤害」这条连锁反应

## 安装

1. 将 `Astrologian` 文件夹放入游戏的 `LocalMods` 目录
   （通常为 `<Steam>/steamapps/common/Barotrauma/LocalMods/`）
2. 启动游戏 → **设置 → 模组** → 启用 `Astrologian`
3. 新建战役时即可在船员界面选择「占星术士」

> 修改任何文件后**必须完全重启游戏**才会生效——天赋树等定义只在启动时加载一次。

## 文件结构

```
Astrologian/
├─ filelist.xml                          内容包清单（模组入口）
├─ Jobs/AstrologianJob.xml               职业定义
├─ TalentTrees/AstrologianTalentTrees.xml 天赋树结构
├─ Talents/AstrologianTalents.xml        天赋实现
├─ Afflictions/AstrologianAfflictions.xml 天赋用的隐藏增益
└─ Text/
   ├─ SimplifiedChinese/SimplifiedChinese.xml
   └─ English/English.xml
```

## 免责声明

本模组为**非官方粉丝作品**，与 Square Enix、FakeFish、Undertow Games 均无关联。
《最终幻想14》及《潜渊症》的相关名称与设定归各自权利人所有。

## 致谢

参考了原版内容与以下模组的设计思路：

- [Talent Enhancement 天赋增强](https://steamcommunity.com/sharedfiles/filedetails/?id=2803561945)（天赋树结构风格）
- [Toxicologist Job](https://steamcommunity.com/sharedfiles/filedetails/?id=2993275947)（随机增益机制的可行性验证）
