[阅读英文版说明](./README.md)

# 冰封之焰 - 游戏专属服务器搭建 V0.1

如您需要搭建《冰封之焰》专属服务器，您需要拥有一台拥有静态IP的服务器，以便于玩家连接至您的服务器加入游玩。

## 进行配置前你需要了解的部分

- 需要开放的网络端口（默认情况下）：

```
25575

27015/udp

27015

7777/udp

7777
```

- 推荐操作系统配置：【请等待后续更新】
-  App ID：`1348640`

## 通过 Steam 客户端配置游戏专属服务器（PC）

1. 首先，你需要在 Steam 资料库中找到“Frozen Flame - Dedicated server”
2. 在安装文件夹中找到 `FrozenFlameServer.exe`
3. 通过命令行模式启动该 exe 文件，并在命令后加入 `-log` （该指令将会为你在命令行上显示游戏控制台信息）

## 在 Linux 系统上搭建游戏专属服务器

1. 首先您需要在服务器上安装 SteamCMD，具体安装步骤请参考[Steam官方文档](https://developer.valvesoftware.com/wiki/SteamCMD:zh-cn)。具体安装步骤请按照具体的 Linux 发行版本（如Ubuntu、Redhat、CentOS）对应。
2. 并按照教程打开 SteamCMD ( [Steam官方文档·运行 SteamCMD 一栏](https://developer.valvesoftware.com/wiki/SteamCMD:zh-cn#.E8.BF.90.E8.A1.8C_SteamCMD))
3. 使用如下 SteamCMD 指令

```
1.    force_install_dir ./frozen_flame/ // 指定 SteamCMD 文件下载位置
2.    login steamaccount //登陆 Steam 账号，可能需要输入密码并需要密保
3.    app_update 1348640 validate //通过 Steam CMD 下载《冰封之焰》服务器端
4.    quit  //退出 Steam CMD
```

## 指令参数

`-log` - 显示游戏控制台
`-LOCALLOGTIMES` - 使用本机系统时间
`-MetaGameServerName=CoolServer` - 设置服务器名字为 `CoolServer`
`RconPassword=password` - 设置 Rcon 密码为 `password`
`RconPort=` - 设置 Rcon 接口

## 配置文件

为配置服务器，你还需要创建 `Game.ini` 文件:
- 对于 Windows：文件需要放到 `Your Dedicated Server Folder\FrozenFlame\Saved\Config\WindowsServer`  文件夹下方
- 对于 Linux：文件需要放到 `Folder\FrozenFlame\Saved\Config\LinuxServer`文件夹下方

文件内容如下（在默认设定下）：

```
[/Script/Engine.GameSession]
MaxPlayers=10
ServerPassword=""

[/Script/FrozenFlame.GameBalance]

# Enable PVP for non-friends
bFreePVP=True

# How long a day lasts
DurationOfDay=3600


# Health after death
HealthAfterRespawn=0.5

# Restore health on level up
bRestoreHealthOnLevelUp=True

# Stamina cost at jumping
JumpStaminaCost=6

# Stamina cost at sprinting
SprintStaminaCost=1

# Loss of armor durability after death
ArmorDurabilityReducementAfterDeath=25

# Weapon durability loss speed
DefaultWeaponDurabilityCost=0.5


# Allow to teleport with overweight
bIsAllowedToTeleportWithOverweight=False

# Allow to fly with overweight
bIsAllowedToGlideWithOverweight=False


# Drop of items after level X
MinimalLevelToDropItemAfterDeath=2147483647

# Drop equipped items after death
bDropEquippedItems=False

# Drop equipable items after death
bDropEquipableItems=False

# Drop food on death
bDropFoodItems=False


#Flame rate from everything
FlameRate=1

#Player damage multiplier
PlayerDamageMultiplier=1

#Monsters health multiplier
MonstersHealthMultiplier=1

#Monsters damage multiplier
MonstersDamageMultiplier=1



#Bulding without material costs
bNoModuleCost=False

#Building without restrictions
bLimitlessSupport=False

#Bulding without decay
bInvulnerableModules=False


[/Script/FrozenFlame.DecaySubsystemSettings]
#A minimum durability that keeps after weather decay system damage
MinDurability=0.300000
```



## RCON

【请等待未来更新】



## F.A.Q.

### 游戏在 20-30 秒闪退了咋办？

1. 请确保服务器支持并打开了 `EasyAntiCheat`，并在客户端启动项中选择了带有 EasyAntiCheat 的启动项。您可以通过检查《冰封之焰》服务器端启动时 Log 是否有打出 `LogEOSAnalytics: Start Session (User: ...)` ，判断是否将其打开
2. 如发现服务器无以上 Log，游戏仍无法正常运行，您可以将服务器端关闭 EasyAntiCheat （如有打开），并在游戏启动时选择不带 EasyAntiCheat 的启动项。



### 游戏存档位置

默认情况下，游戏存档位置为：

```
Frozen Flame - Dedicated Server\FrozenFlame\Saved\SaveGames
```