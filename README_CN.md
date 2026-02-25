# Action RPG 示例项目 - UE5 升级版

[![Unreal Engine](https://img.shields.io/badge/Unreal%20Engine-5.7-black?logo=unrealengine)](https://www.unrealengine.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Android%20%7C%20iOS-lightgrey)](https://github.com)

**[English Documentation](README.md)**

---

> **⚠️ 重要声明**
>
> 本项目是 Epic Games 官方 ActionRPG 示例项目的升级版本。所有原始内容、资产和代码均属于 **Epic Games, Inc.** 本仓库仅供**教育和学习目的**使用。未经 Epic Games 正式授权，不得用于商业用途。
>
> 原项目来源：[Unreal Engine Marketplace - Action RPG](https://www.unrealengine.com/marketplace/en-US/product/action-rpg)

---

## 📋 目录

- [关于本项目](#-关于本项目)
- [功能特性](#-功能特性)
- [环境要求](#-环境要求)
- [安装指南](#-安装指南)
- [升级过程](#-升级过程)
- [项目结构](#-项目结构)
- [已知问题](#-已知问题)
- [贡献指南](#-贡献指南)
- [许可证](#-许可证)
- [致谢](#-致谢)

---

## 🎮 关于本项目

本仓库包含 Epic Games 官方 ActionRPG 示例项目的升级版本，已迁移至 **Unreal Engine 5.7**。ActionRPG 项目演示了如何使用虚幻引擎的强大功能构建动作角色扮演游戏，包括：

- **游戏技能系统 (GAS)** - 一个用于实现技能、属性和效果的强大框架
- **AI 系统** - 行为树和环境查询系统，实现智能敌人行为
- **物品栏系统** - 武器、药水和技能物品的管理
- **战斗系统** - 多种武器类型的近战和远程战斗
- **波次进度系统** - 敌人生成和波次管理

### 🎯 修改原则

本项目遵循**最小化改动原则**：

- ✅ **保留原始设计** - 我们致力于完整保留 Epic ActionRPG 示例的原始设计和架构
- ✅ **兼容性优先** - 修改仅以确保项目能在最新版虚幻引擎中正常运行为目标
- ✅ **不改变功能** - 我们不添加新功能或修改现有游戏机制
- ✅ **纯净升级** - 仅应用必要的 API 更新和弃用修复

### 📅 版本更新

作者会不定期将本项目更新到最新的虚幻引擎稳定版本。更新计划取决于：

- 新版 UE 发布
- 重大 API 变更
- 社区反馈和问题

**欢迎贡献！** 如果您已成功升级到更新的引擎版本或修复了兼容性问题，我们鼓励您提交 Pull Request 来帮助保持项目的时效性。

---

## ✨ 功能特性

### 核心系统

| 功能 | 描述 |
|------|------|
| **游戏技能系统** | 完整实现 GAS，包含技能、属性和游戏效果 |
| **战斗机制** | 剑、锤、斧的近战战斗；火球和陨石技能的远程战斗 |
| **敌人 AI** | 基于行为树的 AI，包含 Boss 战（蜘蛛 Boss） |
| **物品栏与物品** | 数据驱动的武器、药水和技能物品设计 |
| **存档系统** | 持久化的游戏状态和玩家选项 |
| **音频系统** | 完整的声音类和混音器 |

### 支持平台

- Windows (Win64)
- macOS
- Android
- iOS

---

## 🔧 环境要求

### 系统要求

| 要求 | 最低配置 | 推荐配置 |
|------|----------|----------|
| **虚幻引擎** | 5.7 | 5.7+ |
| **操作系统 (Windows)** | Windows 10 64位 | Windows 11 64位 |
| **操作系统 (macOS)** | macOS 12 Monterey | macOS 14 Sonoma |
| **内存** | 16 GB | 32 GB |
| **显卡** | DirectX 11 兼容 | DirectX 12 兼容 |
| **存储空间** | 20 GB | 50 GB (SSD) |

### 软件要求

- **Unreal Engine 5.7** - [从 Epic Games Launcher 下载](https://www.epicgames.com/store/en-US/download)
- **Visual Studio 2022** (Windows) 或 **Xcode 15+** (macOS)
- **Git** - 用于克隆仓库

---

## 📥 安装指南

### 步骤 1：克隆仓库

```bash
git clone https://github.com/YOUR_USERNAME/ActionRPG.git
cd ActionRPG
```

### 步骤 2：生成项目文件

**Windows:**
1. 右键点击 `ActionRPG.uproject`
2. 选择"Generate Visual Studio project files"

**macOS:**
1. 在项目目录中打开终端
2. 运行：`/Users/Shared/UnrealEngine/UE_5.7/Engine/Build/BatchFiles/Mac/GenerateProjectFiles.sh -project="$(pwd)/ActionRPG.uproject" -game -engine`

### 步骤 3：打开项目

1. 双击 `ActionRPG.uproject` 在虚幻编辑器中打开
2. 如果提示，允许引擎重新构建模块
3. 等待着色器编译完成

---

## 🔄 升级过程

本节记录了从原始 UE4/UE5 版本升级到 UE5.7 过程中所做的更改。

### 版本信息

| 组件 | 原始版本 | 升级版本 |
|------|----------|----------|
| 虚幻引擎 | 4.x / 早期 UE5 | **5.7** |
| 引擎关联 | 可变 | **5.7** |

### 执行的升级步骤

#### 1. 项目文件更新

`.uproject` 文件更新内容：
- `EngineAssociation` 更改为 `"5.7"`
- 验证并更新插件兼容性
- 禁用已弃用的插件

#### 2. 构建配置

为 UE5.7 API 更改更新 `Build.cs` 文件：
- 更新模块依赖
- 修复已弃用的 API 调用
- 更新包含路径

#### 3. 代码修改

主要 C++ 更改包括：
- 更新已弃用的函数调用
- 修复游戏技能系统的 API 更改
- 更新物理设置（Chaos 物理引擎）
- 修复导航系统更新

#### 4. 资产迁移

- 所有资产转换为 UE5.7 格式
- 材质更新以支持 Lumen/Nanite（适用处）
- 动画资产重新编译

### 兼容性说明

> **注意：** 以下更改是 UE5.7 兼容性所必需的：

1. **物理引擎**：项目使用 Chaos 物理引擎（UE5 默认）
2. **导航系统**：更新为 `NavigationSystemV1`
3. **渲染**：配置为支持 UE5 特性的移动端友好渲染

---

## 📁 项目结构

```
ActionRPG/
├── Config/                    # 配置文件
│   ├── DefaultEngine.ini      # 引擎设置
│   ├── DefaultGame.ini        # 游戏设置
│   ├── DefaultInput.ini       # 输入映射
│   └── DefaultGameplayTags.ini# 游戏标签
├── Content/                   # 游戏资产
│   ├── Abilities/             # 游戏技能和效果
│   ├── Animations/            # 动画资产
│   ├── Assets/                # 音频和其他资产
│   ├── Blueprints/            # 蓝图类
│   ├── Characters/            # 角色网格和动画
│   └── Effects/               # 视觉效果
├── Source/                    # C++ 源代码
│   ├── ActionRPG/             # 主游戏模块
│   │   ├── Private/           # 实现文件
│   │   └── Public/            # 头文件
│   └── ActionRPGLoadingScreen/# 加载屏幕模块
├── Build/                     # 平台特定构建文件
├── ActionRPG.uproject         # 项目文件
├── README.md                  # 英文文档
├── README_CN.md               # 本文档
├── LICENSE                    # MIT 许可证
└── CONTRIBUTING.md            # 贡献指南
```

### 主要 C++ 类

| 类 | 描述 |
|----|------|
| `RPGCharacterBase` | 带技能系统的基角色类 |
| `RPGGameplayAbility` | 所有游戏技能的基类 |
| `RPGAttributeSet` | 角色属性（生命值、法力值等） |
| `RPGAbilitySystemComponent` | 自定义技能系统组件 |
| `RPGItem` | 物品栏物品的基类 |
| `RPGSaveGame` | 存档功能 |

---

## ⚠️ 已知问题

1. **着色器编译**：首次加载可能需要较长时间进行着色器编译
2. **移动平台**：某些视觉效果在移动设备上可能会简化
3. **VR 插件**：VR 相关插件默认禁用

### 故障排除

| 问题 | 解决方案 |
|------|----------|
| 项目无法打开 | 删除 `Intermediate`、`Saved` 和 `Binaries` 文件夹，然后重新生成项目文件 |
| 编译错误 | 确保安装了带有 UE5.7 工作负载的 Visual Studio 2022 |
| 模块缺失 | 右键点击 `.uproject` 并选择"Generate Visual Studio project files" |

---

## 🤝 贡献指南

欢迎贡献！请阅读我们的[贡献指南](CONTRIBUTING.md)了解我们的行为准则和提交拉取请求的流程。

### 快速贡献步骤

1. Fork 本仓库
2. 创建您的功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

---

## 📄 许可证

本项目采用 MIT 许可证 - 详情请查看 [LICENSE](LICENSE) 文件。

**重要说明：** MIT 许可证仅适用于升级过程中所做的修改和添加。Epic Games ActionRPG 示例项目的所有原始内容仍受 Epic Games 许可条款的约束。

---

## 🙏 致谢

- **Epic Games** - 创建并提供原始 ActionRPG 示例项目
- **虚幻引擎社区** - 持续的支持和文档
- **贡献者** - 所有对本升级版本做出贡献的人

---

## ⭐ 支持本项目

如果您发现本项目对学习虚幻引擎开发有帮助，请考虑：

- ⭐ 给本仓库点星
- 🍴 Fork 用于您自己的项目
- 📢 分享给其他人

---

<div align="center">

**为虚幻引擎社区用 ❤️ 制作**

[返回顶部](#action-rpg-示例项目---ue5-升级版)

</div>
