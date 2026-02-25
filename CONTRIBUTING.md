# Contributing Guidelines

Thank you for your interest in contributing to the ActionRPG UE5 Upgraded Version project! This document provides guidelines and instructions for contributing.

## 📜 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [How to Contribute](#how-to-contribute)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)
- [Reporting Issues](#reporting-issues)

---

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment. We expect all contributors to:

- Be respectful of differing viewpoints
- Accept constructive criticism gracefully
- Focus on what is best for the community
- Show empathy towards other community members

---

## Getting Started

### Prerequisites

Before contributing, ensure you have:

1. **Unreal Engine 5.7** installed
2. **Visual Studio 2022** (Windows) or **Xcode 15+** (macOS)
3. **Git** configured on your system
4. Basic knowledge of Unreal Engine and C++

### Fork and Clone

1. Fork the repository on GitHub
2. Clone your fork locally:

```bash
git clone https://github.com/YOUR_USERNAME/ActionRPG.git
cd ActionRPG
```

3. Add the upstream repository:

```bash
git remote add upstream https://github.com/ORIGINAL_OWNER/ActionRPG.git
```

---

## Development Setup

### Building the Project

1. Generate project files:
   - **Windows**: Right-click `ActionRPG.uproject` → "Generate Visual Studio project files"
   - **macOS**: Run the GenerateProjectFiles script

2. Open the solution/workspace:
   - **Windows**: Open `ActionRPG.sln` in Visual Studio
   - **macOS**: Open the generated Xcode project

3. Build the project in Development Editor configuration

### Keeping Your Fork Updated

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

---

## How to Contribute

### Types of Contributions

We welcome the following types of contributions:

- 🐛 **Bug fixes** - Fix issues in existing code
- ✨ **New features** - Add new functionality
- 📝 **Documentation** - Improve or translate documentation
- 🎨 **Code refactoring** - Improve code quality without changing behavior
- ⚡ **Performance improvements** - Optimize existing code
- 🌐 **Translations** - Add or improve language support

### Before You Start

1. Check existing [issues](../../issues) to avoid duplicate work
2. For major changes, open an issue first to discuss your ideas
3. Make sure your changes align with the project's educational purpose

---

## Coding Standards

### C++ Guidelines

- Follow the [Unreal Engine Coding Standard](https://docs.unrealengine.com/5.7/en-US/epic-cplusplus-coding-standard-for-unreal-engine/)
- Use meaningful variable and function names
- Add comments for complex logic (prefer English for code comments)
- Keep functions focused and reasonably sized

### Blueprint Guidelines

- Follow consistent naming conventions
- Use descriptive variable names
- Add comments to explain complex logic
- Organize nodes logically

### Example Naming Conventions

| Type | Prefix | Example |
|------|--------|---------|
| Blueprint Class | BP_ | BP_PlayerCharacter |
| Widget Blueprint | WB_ | WB_HUD |
| Animation Blueprint | ABP_ | ABP_Player |
| Material | M_ | M_CharacterSkin |
| Material Instance | MI_ | MI_CharacterSkin_Red |
| Texture | T_ | T_CharacterDiffuse |
| Static Mesh | SM_ | SM_WeaponSword |
| Skeletal Mesh | SK_ | SK_Character |

---

## Commit Guidelines

### Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation changes |
| `style` | Code style changes (formatting, etc.) |
| `refactor` | Code refactoring |
| `perf` | Performance improvements |
| `test` | Adding or modifying tests |
| `chore` | Maintenance tasks |

### Examples

```
feat(combat): add dodge roll ability

- Implement dodge roll animation
- Add invulnerability frames during roll
- Configure dodge cooldown

Closes #123
```

```
fix(ai): fix enemy not detecting player

Fixed an issue where enemies would not detect the player
when approaching from certain angles.

Fixes #456
```

---

## Pull Request Process

### Before Submitting

1. **Update your branch** with the latest upstream changes
2. **Test your changes** thoroughly in the editor
3. **Build the project** to ensure no compilation errors
4. **Update documentation** if needed

### Submitting a Pull Request

1. Push your changes to your fork:

```bash
git push origin your-feature-branch
```

2. Open a Pull Request on GitHub
3. Fill in the PR template with:
   - Description of changes
   - Related issue numbers
   - Testing performed
   - Screenshots (if applicable)

### PR Review Process

1. Maintainers will review your PR
2. Address any feedback or requested changes
3. Once approved, your PR will be merged

### Checklist

- [ ] Code compiles without errors
- [ ] Changes tested in Unreal Editor
- [ ] Documentation updated (if applicable)
- [ ] Commit messages follow guidelines
- [ ] No unnecessary files included

---

## Reporting Issues

### Before Reporting

1. Search existing issues to avoid duplicates
2. Test with the latest version of the project
3. Gather relevant information

### Issue Template

When reporting an issue, include:

**Description**
A clear description of the issue.

**Steps to Reproduce**
1. Go to '...'
2. Click on '....'
3. See error

**Expected Behavior**
What you expected to happen.

**Actual Behavior**
What actually happened.

**Environment**
- OS: [e.g., Windows 11]
- Unreal Engine Version: [e.g., 5.7]
- Visual Studio Version: [e.g., 2022 17.8]

**Screenshots**
If applicable, add screenshots.

**Additional Context**
Any other relevant information.

---

## Questions?

If you have questions about contributing, feel free to:

- Open an issue with the "question" label
- Start a discussion in the Discussions section

---

Thank you for contributing to this project! Your efforts help make this a better learning resource for the Unreal Engine community.

---

**[中文版贡献指南](CONTRIBUTING_CN.md)** (if available)
