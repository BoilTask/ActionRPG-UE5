# Action RPG Sample Project - UE5 Upgraded Version

[![Unreal Engine](https://img.shields.io/badge/Unreal%20Engine-5.7-black?logo=unrealengine)](https://www.unrealengine.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Android%20%7C%20iOS-lightgrey)](https://github.com)

**[中文文档 (Chinese Documentation)](README_CN.md)**

---

> **⚠️ IMPORTANT NOTICE**
>
> This project is an upgraded version of the official Epic Games ActionRPG sample project. All original content, assets, and code belong to **Epic Games, Inc.** This repository is intended for **educational and learning purposes only**. No commercial use is permitted without proper authorization from Epic Games.
>
> Original Project Source: [Unreal Engine Marketplace - Action RPG](https://www.unrealengine.com/marketplace/en-US/product/action-rpg)

---

## 📋 Table of Contents

- [About The Project](#-about-the-project)
- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Upgrade Process](#-upgrade-process)
- [Project Structure](#-project-structure)
- [Known Issues](#-known-issues)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## 🎮 About The Project

This repository contains an upgraded version of the official ActionRPG sample project from Epic Games, migrated to **Unreal Engine 5.7**. The ActionRPG project demonstrates how to build an action role-playing game using Unreal Engine's powerful features, including:

- **Gameplay Ability System (GAS)** - A robust framework for implementing abilities, attributes, and effects
- **AI System** - Behavior trees and environment queries for intelligent enemy behavior
- **Inventory System** - Item management with weapons, potions, and skills
- **Combat System** - Melee and ranged combat with various weapon types
- **Wave-based Progression** - Enemy spawning and wave management

---

## ✨ Features

### Core Systems

| Feature | Description |
|---------|-------------|
| **Gameplay Ability System** | Complete implementation of GAS with abilities, attributes, and gameplay effects |
| **Combat Mechanics** | Melee combat with swords, hammers, and axes; ranged combat with fireballs and meteor skills |
| **Enemy AI** | Behavior tree-driven AI with boss encounters (Spider Boss) |
| **Inventory & Items** | Weapons, potions, and skill items with data-driven design |
| **Save System** | Persistent game state and player options |
| **Audio System** | Comprehensive sound classes and mixers |

### Supported Platforms

- Windows (Win64)
- macOS
- Android
- iOS

---

## 🔧 Prerequisites

### System Requirements

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| **Unreal Engine** | 5.7 | 5.7+ |
| **OS (Windows)** | Windows 10 64-bit | Windows 11 64-bit |
| **OS (macOS)** | macOS 12 Monterey | macOS 14 Sonoma |
| **RAM** | 16 GB | 32 GB |
| **GPU** | DirectX 11 compatible | DirectX 12 compatible |
| **Storage** | 20 GB | 50 GB (SSD) |

### Software Requirements

- **Unreal Engine 5.7** - [Download from Epic Games Launcher](https://www.epicgames.com/store/en-US/download)
- **Visual Studio 2022** (Windows) or **Xcode 15+** (macOS)
- **Git** - For cloning the repository

---

## 📥 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/ActionRPG.git
cd ActionRPG
```

### Step 2: Generate Project Files

**Windows:**
1. Right-click on `ActionRPG.uproject`
2. Select "Generate Visual Studio project files"

**macOS:**
1. Open Terminal in the project directory
2. Run: `/Users/Shared/UnrealEngine/UE_5.7/Engine/Build/BatchFiles/Mac/GenerateProjectFiles.sh -project="$(pwd)/ActionRPG.uproject" -game -engine`

### Step 3: Open the Project

1. Double-click `ActionRPG.uproject` to open in Unreal Editor
2. If prompted, allow the engine to rebuild modules
3. Wait for shader compilation to complete

---

## 🔄 Upgrade Process

This section documents the changes made during the upgrade from the original UE4/UE5 version to UE5.7.

### Version Information

| Component | Original Version | Upgraded Version |
|-----------|------------------|------------------|
| Unreal Engine | 4.x / Early UE5 | **5.7** |
| Engine Association | Variable | **5.7** |

### Upgrade Steps Performed

#### 1. Project File Updates

The `.uproject` file was updated with:
- `EngineAssociation` changed to `"5.7"`
- Plugin compatibility verified and updated
- Deprecated plugins disabled

#### 2. Build Configuration

Updated `Build.cs` files for UE5.7 API changes:
- Updated module dependencies
- Fixed deprecated API calls
- Updated include paths

#### 3. Code Modifications

Key C++ changes include:
- Updated deprecated function calls
- Fixed API changes in Gameplay Ability System
- Updated physics settings (Chaos Physics)
- Fixed navigation system updates

#### 4. Asset Migration

- All assets converted to UE5.7 format
- Materials updated for Lumen/Nanite compatibility (where applicable)
- Animation assets recompiled

### Compatibility Notes

> **Note:** The following changes were necessary for UE5.7 compatibility:

1. **Physics Engine**: The project uses Chaos Physics (default in UE5)
2. **Navigation System**: Updated to `NavigationSystemV1`
3. **Rendering**: Configured for mobile-friendly rendering with UE5 features

---

## 📁 Project Structure

```
ActionRPG/
├── Config/                    # Configuration files
│   ├── DefaultEngine.ini      # Engine settings
│   ├── DefaultGame.ini        # Game settings
│   ├── DefaultInput.ini       # Input mappings
│   └── DefaultGameplayTags.ini# Gameplay tags
├── Content/                   # Game assets
│   ├── Abilities/             # Gameplay abilities and effects
│   ├── Animations/            # Animation assets
│   ├── Assets/                # Audio and other assets
│   ├── Blueprints/            # Blueprint classes
│   ├── Characters/            # Character meshes and animations
│   └── Effects/               # Visual effects
├── Source/                    # C++ source code
│   ├── ActionRPG/             # Main game module
│   │   ├── Private/           # Implementation files
│   │   └── Public/            # Header files
│   └── ActionRPGLoadingScreen/# Loading screen module
├── Build/                     # Platform-specific build files
├── ActionRPG.uproject         # Project file
├── README.md                  # This file
├── README_CN.md               # Chinese documentation
├── LICENSE                    # MIT License
└── CONTRIBUTING.md            # Contribution guidelines
```

### Key C++ Classes

| Class | Description |
|-------|-------------|
| `RPGCharacterBase` | Base character class with ability system |
| `RPGGameplayAbility` | Base class for all gameplay abilities |
| `RPGAttributeSet` | Character attributes (Health, Mana, etc.) |
| `RPGAbilitySystemComponent` | Custom ability system component |
| `RPGItem` | Base class for inventory items |
| `RPGSaveGame` | Save game functionality |

---

## ⚠️ Known Issues

1. **Shader Compilation**: Initial load may take time due to shader compilation
2. **Mobile Platforms**: Some visual effects may be simplified on mobile devices
3. **VR Plugins**: VR-related plugins are disabled by default

### Troubleshooting

| Issue | Solution |
|-------|----------|
| Project won't open | Delete `Intermediate`, `Saved`, and `Binaries` folders, then regenerate project files |
| Compilation errors | Ensure Visual Studio 2022 with UE5.7 workload is installed |
| Missing modules | Right-click `.uproject` and select "Generate Visual Studio project files" |

---

## 🤝 Contributing

Contributions are welcome! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

### Quick Contribution Steps

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Important:** The MIT License applies only to the modifications and additions made during the upgrade process. All original content from Epic Games' ActionRPG sample project remains subject to Epic Games' licensing terms.

---

## 🙏 Acknowledgments

- **Epic Games** - For creating and providing the original ActionRPG sample project
- **Unreal Engine Community** - For continuous support and documentation
- **Contributors** - Everyone who has contributed to this upgraded version

---

## ⭐ Show Your Support

If you find this project helpful for learning Unreal Engine development, please consider:

- ⭐ Starring this repository
- 🍴 Forking it for your own projects
- 📢 Sharing it with others

---

<div align="center">

**Made with ❤️ for the Unreal Engine Community**

[Back to Top](#action-rpg-sample-project---ue5-upgraded-version)

</div>
