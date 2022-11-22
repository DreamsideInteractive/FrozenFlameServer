[阅读中文版本](LocalCoopSettings.md)

# 《冰封之焰》 - 本地联机模式设定

在等待开发团队处理游戏内设置UI的这段时间内，你可以通过更改本地联机的配置文件进行这一模式下的配置设定。

为保证本地联机模式下配置文件能够成功生效，请通过[本链接](Game.ini)下载默认的设定文档。本地的配置文档文件夹目录为：`%USERPROFILE%/AppData/Local/FrozenFlame/Saved/Config/WindowsNoEditor`。

在文件放置在指定的文件夹下后，你便可以通过修改 `Game.ini` 文件更改本地联机模式下的游戏设置。

**请注意，由于部分配置并未生效，因此使用配置文件直接修改存在一定的风险。在修改游戏配置之前，我们建议您备份您的游戏存档以免存档彻底丢失或损坏**

## 配置文档说明

|配置文本|中文注释|默认值|
|---|---|---|
|bFreePVP|对非好友开放 PVP|True|
|DurationOfDay|游戏内一日的时长为|3600|
|HealthAfterRespawn|死亡复活时的 HP|0.5|
|bRestoreHealthOnLevelUp|等级提升时恢复的 HP|True|
|JumpStaminaCost|跳跃时消耗的体力值|6|
|SprintStaminaCost|冲刺时消耗的体力值|1|
|ArmorDurabilityReducementAfterDeath|因死亡消耗的装甲耐久度|25|
|DefaultWeaponDurabilityCost|武器耐久度消耗速度|0.5|
|HalfSlowdownOverweightRatio|过重 - 玩家将在一定负重的情况下无法奔跑(默认：200/100%)|1|
|FullSlowdownOverweightRatio|过重 - 玩家将在一定负重的情况下无法奔跑、无法获得新物品（默认：300/150%）|1.5|
|bIsAllowedToTeleportWithOverweight|是否允许过重状态下进行传送|False|
|bIsAllowedToGlideWithOverweight|是否允许过重状态下飞行|False|
|MinimalLevelToDropItemAfterDeath|Drop of items after level X|2147483647|
|bDropEquippedItems|是否在死亡后掉落物品|False|
|bDropEquipableItems|是否在死亡后掉落装备|False|
|bDropFoodItems|是否在死亡后掉落食物|False|
|FlameRate|Flame rate from everything|1|
|PlayerDamageMultiplier|玩家伤害倍率|1|
|MonstersHealthMultiplier|怪物 HP 倍率|1|
|MonstersDamageMultiplier|怪物伤害倍率|1|
|bNoModuleCost|是否开启无消耗建造模式|False|
|bLimitlessSupport|是否开启无限制建造模式|False|
|bInvulnerableModules|是否开启建造物无侵蚀模式|False|
|bDemolishResourceDropMultiplier|当建筑物摧毁时多少资源将会回收|0.5|

**建筑老化性设置**

|配置文本|中文注释|默认值|
|---|---|---|
|MinDurability|在极端天气老化下，建筑的最低耐久值|0.3|

**默认基础设定**

|配置文本|中文注释|默认值|
|---|---|---|
|bDisableOverweight|是否关闭过重系统|false|

**BP_GameBalance_Base.BP_GameBalance_Base_C**

|配置文本|中文注释|默认值|
|---|---|---|
|bApplyRestrictionsInsideEnergyBarriers|在能量屏障区域内是否开启飞行与建筑限制|1|

