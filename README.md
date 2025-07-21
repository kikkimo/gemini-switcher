# Gemini Switcher

An elegant interactive authentication manager for Google's Gemini CLI with a beautiful Gemini-CLI-style interface. Manage multiple Gemini API credentials and switch between them seamlessly.

## 📖 Documentation

- [English](README.md) (Current)
- [中文文档](docs/README-zh.md)

## ✨ Features

- 🎨 **Claude-style interface** with authentic gemini blue color scheme
- ⌨️ **Arrow key navigation** with fallback to number selection
- 🔐 **Encrypted credential storage** using AES-256-CBC encryption
- 🔄 **Multi-credential management** - Add, remove, and switch between authentications
- 🌍 **Global installation** - use `gemini-switcher` from anywhere
- 🔧 **Smart environment setup** - automatically configures shell environment variables
- 💻 **Cross-platform** - Windows, macOS, and Linux support

## 🚀 Quick Start

1. **Install globally:**
   ```bash
   npm install -g @kikkimo/gemini-switcher
   ```

2. **Run the switcher:**
   ```bash
   gemini-switcher
   ```

3. **Add your first authentication:** Enter your Google API key (starting with `AIza`) and Google Cloud Project ID when prompted

That's it! The switcher will guide you through the setup process.

## 📦 Installation

### Global Installation (Recommended)

```bash
npm install -g @kikkimo/gemini-switcher
```

After installation, you can run `gemini-switcher` from any directory.

### Local Installation

```bash
git clone https://github.com/kikkimo/gemini-switcher.git
cd gemini-switcher
npm install
node gemini-switcher
```

## 🎮 Usage

### Available Authentication Options

1. **Add New Gemini Authentication** - Add new Google API key and Cloud Project ID
2. **Remove Gemini Authentication** - Remove existing authentication with table navigation
3. **Switch Gemini Authentication** - Select and activate authentication (sets system environment variables)
4. **Exit** - Generate shell commands to set environment variables for current session

### Interactive Navigation

- **Arrow Keys**: Use ↑↓ to navigate, Enter to select (in TTY environments)
- **Number Selection**: Type 1-4 and press Enter (in non-TTY environments)
- **Quick Exit**: Press Esc or Q to quit anytime

### Example Session

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

## ⚙️ Configuration

### Automatic Configuration

On first run, the switcher will:

1. Automatically create `authentications.json` in the installation directory
2. Guide you through entering your Google API key and Cloud Project ID
3. Encrypt and store your credentials securely using machine-specific encryption

### Manual Configuration

The configuration file `authentications.json` stores encrypted credentials:

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

**Note**: All credentials are automatically encrypted when entered through the switcher. Do not manually edit encrypted values.

### Security Features

- **AES-256-CBC Encryption**: Credentials are encrypted using industry-standard encryption
- **Machine-specific Keys**: Encryption keys are derived from machine-specific data
- **Local Storage Only**: Encrypted credentials cannot be decrypted on other machines
- **Secure Input**: API key input supports copy/paste and validation

## 📋 Requirements

- **Node.js**: 20.0.0 or higher
- **Gemini CLI**: Installed and accessible via `gemini` command
- **Terminal**: Any modern terminal with Node.js support

## 🔧 Development

### Building from Source

```bash
git clone https://github.com/kikkimo/gemini-switcher.git
cd gemini-switcher
npm install
```

### Testing Locally

```bash
npm start
# or
node gemini-switcher
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with ❤️ for the Gemini CLI community
- Thanks to all contributors and users

## 🐛 Issues & Support

If you encounter any issues or have questions:

1. Check existing [Issues](https://github.com/kikkimo/gemini-switcher/issues)
2. Create a new issue with detailed information
3. Include your operating system, Node.js version, and error messages

---

**Note**: This switcher is designed to work with Google's Gemini CLI. Make sure you have the Gemini CLI installed before using this tool.