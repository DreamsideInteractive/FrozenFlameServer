[阅读英文版教程](./README.md)

# 冰封之焰 - 游戏专属服务器搭建 V0.3.6

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
- App ID：`1348640`
- 经过中国 2P Games 团队进行的搭建测试，我们推荐使用内存 4G 以上的服务器进行搭建，否则搭建过程将会由于内存不足以游戏渲染导致虚幻引擎内存报错关闭。
- 同时对于使用阿里云、腾讯云搭建服务器的玩家们，我们建议你在搭建前检查云服务器安全组规则保证游戏必要的 TCP 与 UDP 协议端口有为所有人（如有需求）打开

## 在 Windows 系统上搭建游戏专属服务器

### 依赖文件：

- 在 Windows 系统上执行游戏文件将会需要使用到的依赖包：
  - [Direct X](http://www.microsoft.com/en-us/download/confirmation.aspx?id=8109)
    - 下载完毕后先进行一次解压，解压完毕后点击 exe 文件进行安装
  - [Visual C++](https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-160)
    - 在页面上选择对应服务器系统版本的安装包进行安装
  - [Steam 客户端（没错，你没看错）](https://store.steampowered.com/about/)
    - 经过测试，目前版本玩家需要安装 Steam 客户端才能完成游戏服务器端的用户信息
    - 在完成安装操作之后，可以直接将 Steam 客户端直接关闭，不需要进行登录

### 步骤一：下载安装 SteamCMD

1. 首先你需要在服务器上安装 SteamCMD，从服务器上[使用本链接进行 SteamCMD 下载](https://steamcdn-a.akamaihd.net/client/installer/steamcmd.zip)
2. 提取 `SteamCMD.zip` 中的文件到 `C:\steamcmd` 目录下
3. 打开 Windows PowerShell 执行以下命令，启动 SteamCMD

```
cd C:\steacmd
.\steamcmd.exe
```

### 步骤二：通过 SteamCMD 下载安装游戏

完成步骤二的操作后，执行以下指令

```
1.    force_install_dir C:\frozen_flame\ // 指定 SteamCMD 文件下载位置
2.    login anonymous //登陆 Steam 匿名账号，此步骤可能需要等待一段时间完成
3.    app_update 1348640 validate //通过 Steam CMD 下载《冰封之焰》服务器端
4.    quit  //退出 Steam CMD
```

完成上述步骤后，《冰封之焰》服务器端就将安装至你的 Windows 服务器上

### 步骤三：运行游戏

打开 Windows Powershell，执行以下命令启动游戏

```
cd C:\frozen_flame\
.\FrozenFlameServer.exe -log
```

将会弹出新窗口开设服务器房间。

在首次运行了《冰封之焰》服务器端文件的后，游戏将会在服务器创建所需要的相关文件，并在端口 7777 下方创建游戏房间

在我们的测试中有出现以下情况：

- 如成功看到 LogTemp: WorldSaved, 52 entities, 0 ModuleClusters, 则代表房间成功创建。
- 如看到报错 `Engine crash handling finished; re-raising signal 11 for the default handler. Good bye.`, 则代表游戏创建失败，虚幻引擎执行了游戏关闭步骤
  - 如报错  `Executing StaticShutdownAfterError` 以及类似 `LargeMemoryPoolOffset`的字样，则代表服务器的内存不足导致的游戏创建失败，您可以通过为服务器增加内存的方法解决。（在我们的测试中成功创建游戏房间的服务器内存为 4G）
- 如看到报错 `LogSteamShared: Warning: Steam Dedicated Server API failed to initialize`，则代表游戏未能执行 Steam API。（在我们的测试中，通过安装 Steam 客户端帮助了这一命令的执行）


## 在 Linux 系统上搭建游戏专属服务器

### 依赖文件：

> 2P Games 团队将会在后续对此部分进行更新

### 步骤一：通过 SteamCMD 下载安装游戏

1. 首先您需要在服务器上安装 SteamCMD，具体安装步骤请参考[Steam官方文档](https://developer.valvesoftware.com/wiki/SteamCMD:zh-cn)。具体安装步骤请按照具体的 Linux 发行版本（如Ubuntu、Redhat、CentOS）对应。
2. 并按照教程打开 SteamCMD ( [Steam官方文档·运行 SteamCMD 一栏](https://developer.valvesoftware.com/wiki/SteamCMD:zh-cn#.E8.BF.90.E8.A1.8C_SteamCMD))
3. 使用如下 SteamCMD 指令

```
1.    force_install_dir ./frozen_flame/ // 指定 SteamCMD 文件下载位置
2.    login anonymous //登陆 Steam 匿名账号，此步骤可能需要等待一段时间完成
3.    app_update 1348640 validate //通过 Steam CMD 下载《冰封之焰》服务器端
4.    quit  //退出 Steam CMD
```

> 我们推荐您根据 Steam 官方文档创建子账户完成 SteamCMD 的下载安装步骤（而非使用 Root 账号），您可以通过检查命令行“@”号前方的名称判断用户
> 
> 为何我们需要使用 SteamCMD 安装游戏：由于游戏客户端与服务器端的游戏需要保持最新版本才能保证游戏的正常运行，因此我们选择使用 Steam 为我们进行游戏的服务器端的更新步骤

### 步骤二：执行游戏服务器端运行脚本

完成上述步骤后，游戏就将安装至我们指定的 /frozen_flame 文件夹下方，随后执行下述步骤：

```
1. cd frozen_flame/ //进入 frozen_flame 文件夹
2. ./FrozenFlameServer.sh -log //运行《冰封之焰》服务器端

```

在首次运行了《冰封之焰》服务器端文件的后，游戏将会在服务器创建所需要的相关文件，并在端口 7777 下方创建游戏房间

在我们的测试中有出现以下情况：

- 如成功看到 LogTemp: WorldSaved, 52 entities, 0 ModuleClusters, 则代表房间成功创建。
- 如看到报错 `Engine crash handling finished; re-raising signal 11 for the default handler. Good bye.`, 则代表游戏创建失败，虚幻引擎执行了游戏关闭步骤
  - 如报错  `Executing StaticShutdownAfterError` 以及类似 `LargeMemoryPoolOffset`的字样，则代表服务器的内存不足导致的游戏创建失败，您可以通过为服务器增加内存的方法解决。（在我们的测试中成功创建游戏房间的服务器内存为 4G）

## FrozenFlameServer 指令参数

- `-log` - 显示运行报告
- `-LOCALLOGTIMES` - 使用本机系统时间
- `-port` - 设置服务器连接端口
- `-ip` - 设置 IP
- `-MetaGameServerName=CoolServer` - 设置服务器名字为 `CoolServer`
- `-noeac` - 以无 EasyAntiCheat （EAC，蓝熊）模式启动服务端游戏（该模式下需要客户端游戏也以无 EasyAntiCheat 模式打开游戏）
- `RconPassword=password` - 设置 Rcon 密码为 `password`
- `RconPort=` - 设置 Rcon 接口

## 配置文件

游戏的配置文件名为 `Game.ini` ， 你可以从[这里](./Game.ini)下载到默认的 `Game.ini` 文件。对于不同的系统，这一文件需要放置在不同的文件夹下。

### 配置文件位置：

- 对于 Windows：你可以找到配置文件位于 `Your Dedicated Server Folder\FrozenFlame\Saved\Config\WindowsServer`  文件夹下方
- 对于 Linux：你可以找到配置文件位于 `Folder\FrozenFlame\Saved\Config\LinuxServer`文件夹下方

### 你需要了解的部分：

- 配置文件将会在首次执行服务器端启动的时候进行创建
- 配置文件将会在游戏重启时进行加载，但请保证在游戏完全关闭时进行修改游戏配置文件，并在重新开启游戏服务器前确认是否成功完成了游戏配置文件的修改
  - 请务必注意游戏文件配置文件的格式

**游戏平衡性配置**

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

## RCON

【请等待未来更新】



## F.A.Q.

### 游戏在 20-30 秒闪退了咋办？

1. 请确保服务器支持并打开了 `EasyAntiCheat`，并在客户端启动项中选择了带有 EasyAntiCheat 的启动项。您可以通过检查《冰封之焰》服务器端启动时 Log 是否有打出 `LogEOSAnalytics: Start Session (User: ...)` ，判断是否将其打开
2. 如发现服务器无以上 Log，游戏仍无法正常运行，您可以将服务器端关闭 EasyAntiCheat （如有打开），并在游戏启动时选择不带 EasyAntiCheat 的启动项。

EAC 关闭方法： 在启用游戏时以以下命令启动 
- Linux 系统下：`./FrozenFlameServer.sh -log -noeac`
- Windows 系统下：`.\FrozenFlameServer.exe -log -noeac`


### 游戏新手教程之后的门进不去怎么办？

对于 Windows 服务器，在我们的测试中是由于服务器端无法使用 Steam API 而导致的问题。就目前而言，最简单的操作是安装 Steam 客户端。

### 游戏存档位置

默认情况下，游戏存档位置为：

```
Frozen Flame - Dedicated Server\FrozenFlame\Saved\SaveGames
```

---

如您在游玩/搭建过程中遇到任何问题，或是想要找到伙伴一起开黑。

欢迎加入 2P Games 官方《冰封之焰》玩家群：398937562