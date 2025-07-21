# Gemini Switcher

一个优雅的 Google Gemini CLI 认证管理器，具有美观的 Gemini 风格界面。管理多个 Gemini API 凭据并在它们之间无缝切换。

## 📖 文档

- [English](../README.md)
- [中文文档](README-zh.md) (当前)

## ✨ 特性

- 🎨 **Claude 风格界面** - 采用正宗的 Gemini 蓝配色方案
- ⌨️ **方向键导航** - 支持方向键导航，非 TTY 环境下支持数字选择
- 🔐 **加密凭据存储** - 使用 AES-256-CBC 加密
- 🔄 **多凭据管理** - 添加、删除和切换认证
- 🌍 **全局安装** - 在任何地方都可以使用 `gemini-switcher`
- 🔧 **智能环境设置** - 自动配置 Shell 环境变量
- 💻 **跨平台支持** - Windows、macOS 和 Linux

## 🚀 快速开始

1. **全局安装:**
   ```bash
   npm install -g @kikkimo/gemini-switcher
   ```

2. **运行切换器:**
   ```bash
   gemini-switcher
   ```

3. **添加您的第一个认证:** 按提示输入您的 Google API 密钥（以 `AIza` 开头）和 Google Cloud 项目 ID

就这么简单！切换器会引导您完成设置过程。

## 📦 安装

### 全局安装（推荐）

```bash
npm install -g @kikkimo/gemini-switcher
```

安装后，您可以在任何目录运行 `gemini-switcher`。

### 本地安装

```bash
git clone https://github.com/kikkimo/gemini-switcher.git
cd gemini-switcher
npm install
node gemini-switcher
```

## 🎮 使用方法

### 可用认证选项

1. **Add New Gemini Authentication** - 添加新的 Google API 密钥和 Cloud 项目 ID
2. **Remove Gemini Authentication** - 通过表格导航删除现有认证
3. **Switch Gemini Authentication** - 选择并激活认证（设置系统环境变量）
4. **Exit** - 生成 Shell 命令为当前会话设置环境变量

### 交互式导航

- **方向键**：使用 ↑↓ 导航，Enter 选择（在 TTY 环境中）
- **数字选择**：输入 1-4 并按 Enter（在非 TTY 环境中）
- **快速退出**：随时按 Esc 或 Q 退出

### 示例会话

```bash
$ gemini-switcher

  ┌────────────────────────────────────────┐
  │       Gemini Environment Switcher      │
  └────────────────────────────────────────┘

  Use ↑↓ arrow keys to navigate, Enter to select

  → Add New Gemini Authentication
    Remove Gemini Authentication
    Switch Gemini Authentication
    Exit
```

## ⚙️ 配置

### 自动配置

首次运行时，切换器将：

1. 自动在安装目录创建 `authentications.json`
2. 引导您输入 Google API 密钥和 Cloud 项目 ID
3. 使用机器特定的加密安全存储您的凭据

### 手动配置

配置文件 `authentications.json` 存储加密凭据：

```json
{
  "authentications": [
    {
      "apiKey": "encrypted_api_key_here",
      "projectId": "encrypted_project_id_here"
    }
  ]
}
```

**注意**: 所有凭据通过切换器输入时会自动加密。请勿手动编辑加密值。

### 安全功能

- **AES-256-CBC 加密**: 使用行业标准加密算法加密凭据
- **机器特定密钥**: 加密密钥从机器特定数据派生
- **仅本地存储**: 加密凭据无法在其他机器上解密
- **安全输入**: API 密钥输入支持复制/粘贴和验证

## 📋 系统要求

- **Node.js**: 20.0.0 或更高版本
- **Gemini CLI**: 已安装并可通过 `gemini` 命令访问
- **终端**: 任何支持 Node.js 的现代终端

## 🔧 开发

### 从源码构建

```bash
git clone https://github.com/kikkimo/gemini-switcher.git
cd gemini-switcher
npm install
```

### 本地测试

```bash
npm start
# 或者
node gemini-switcher
```

## 🤝 贡献

我们欢迎贡献！请遵循以下步骤：

1. Fork 这个仓库
2. 创建您的功能分支：`git checkout -b feature/amazing-feature`
3. 提交您的更改：`git commit -m 'Add amazing feature'`
4. 推送到分支：`git push origin feature/amazing-feature`
5. 打开一个 Pull Request

## 📄 许可证

此项目基于 MIT 许可证 - 查看 [LICENSE](../LICENSE) 文件了解详情。

## 🙏 致谢

- 用 ❤️ 为 Gemini CLI 社区构建
- 感谢所有贡献者和用户

## 🐛 问题与支持

如果您遇到任何问题或有疑问：

1. 查看现有的 [Issues](https://github.com/kikkimo/gemini-switcher/issues)
2. 创建新问题并提供详细信息
3. 包含您的操作系统、Node.js 版本和错误消息

---

**注意**: 此切换器设计用于 Google 的 Gemini CLI。使用此工具前请确保已安装 Gemini CLI。