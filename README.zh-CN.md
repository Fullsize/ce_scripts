# Cheat Engine 游戏修改表：欧卡 2、红警 2 等

[English](README.md) | **简体中文**

本仓库收集用于在 Windows 上查看和修改游戏内存的 **Cheat Engine 修改表（`.CT` 文件）**，包含 **欧洲卡车模拟 2（Euro Truck Simulator 2）**、**命令与征服：红色警戒 2（Red Alert 2）**、**尤里的复仇（Yuri's Revenge）**，以及一个疑似用于 **植物大战僵尸（Plants vs. Zombies）** 的表。

文件保存的是内存地址和指针链，可直接使用 Cheat Engine 打开和编辑。仓库未附带独立修改器程序、Lua 脚本或 Auto Assembler 脚本。

## 修改表列表

| 游戏 | 文件 | 条目 | 目标进程 |
| --- | --- | --- | --- |
| 欧洲卡车模拟 2（ETS2 / 欧卡 2） | [eurotrucks2.CT](eurotrucks2.CT) | 金钱、经验 | `eurotrucks2.exe` |
| 命令与征服：红色警戒 2（RA2 / 红警 2） | [red2.CT](red2.CT) | 电量、金钱、电量负载 | `game.exe` |
| 红色警戒 2：尤里的复仇 | [red2_yuir.CT](red2_yuir.CT) | 金钱 | `gamemd.exe` |
| 植物大战僵尸（疑似目标，尚未确认） | [zhiwu.CT](zhiwu.CT) | 两个未命名条目，具体用途未记录 | `popcapgame1.exe` |

文件名沿用仓库中的原始名称，包括 `red2_yuir.CT`。表内条目描述目前为中文，所有条目的数值类型均为 **4 Bytes（4 字节）**。

## 快速开始

1. 在 Windows 上安装 [Cheat Engine](https://www.cheatengine.org/)。
2. 在 [GitHub 仓库](https://github.com/Fullsize/ce_scripts) 点击 **Code → Download ZIP** 下载，或使用 Git 克隆：

   ```sh
   git clone https://github.com/Fullsize/ce_scripts.git
   ```

3. 启动游戏，载入存档或进入一局游戏，让游戏数据完成初始化。
4. 在 Cheat Engine 中通过 **File → Load** 打开对应的 `.CT` 文件；如果已关联 `.CT` 文件，也可以直接双击打开。
5. 使用 Cheat Engine 的进程选择器，连接上表中对应的游戏进程。
6. 先确认表内数值与游戏中的数值一致，再双击 **Value（数值）** 修改。对于能正常解析的条目，可以勾选复选框冻结数值。

修改前请备份存档。`zhiwu.CT` 的两个条目需要先确认用途，再进行修改。

## 兼容性说明

这些表使用固定的模块相对地址和指针偏移。不同游戏版本、可执行文件或模组可能改变内存布局，导致条目失效。

- **游戏版本：** 尚未记录准确的适用版本，也未完成跨版本兼容性验证。
- **Cheat Engine 版本：** XML 文件声明了 `CheatEngineTableVersion="45"`。这是表格式标识，不能据此认定最低支持的软件版本。
- **运行平台：** 表内引用的是 Windows `.exe` 进程，尚未验证其他平台或兼容层。
- **植物大战僵尸：** 文件名和进程名指向该游戏，但表内未记录具体游戏版本及两个条目的修改目标。

## 常见问题

| 现象 | 排查方法 |
| --- | --- |
| 数值显示为 `??` | 确认连接了正确进程，并已进入游戏。如果仍无法解析，指针链可能不适用于当前版本。 |
| 数值与游戏中不一致 | 检查游戏进程和版本；修改前确认该条目实际代表的数值。 |
| 游戏更新后失效 | 可能需要为新版本重新定位基址或指针偏移。 |
| 尤里的复仇条目无法解析 | 连接 `gamemd.exe`；红警 2 的表使用的是 `game.exe`。 |

## 目录结构

```text
ce_scripts/
├── README.md          # 英文文档（默认）
├── README.zh-CN.md    # 简体中文文档
├── eurotrucks2.CT     # 欧卡 2：金钱、经验
├── red2.CT            # 红警 2：电量、金钱、电量负载
├── red2_yuir.CT       # 尤里的复仇：金钱
└── zhiwu.CT           # 面向 popcapgame1.exe 的两个未命名条目
```

## 参与完善

欢迎通过 [Issue](https://github.com/Fullsize/ce_scripts/issues) 或 Pull Request 提交文档纠正、更新后的指针链及已验证的游戏版本。

反馈兼容性问题时，请提供表文件名、游戏版本、进程名、Cheat Engine 版本和出问题的条目。更新修改表时，请说明各条目的用途及实际测试的游戏版本。涉及已记录功能的变更，请同步更新中英文文档。
