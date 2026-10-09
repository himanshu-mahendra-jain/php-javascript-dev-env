# PHP & JavaScript Development Environment

A modern PHP & JavaScript Development Environment with multiple deployment options and automated setup scripts. This project includes support for GitHub Codespaces, and Local System Installation.

## Project Structure

```
php-javascript-dev-env/
├── .devcontainer/                      # GitHub Codespaces configuration
│   ├── Containerfile                   # Docker container definition
│   └── devcontainer.json               # VS Code dev container settings
├── local/                              # Local system installation
│   └── local-setup.sh                  # Automated setup script
├── LICENSE                             # MIT license
└── README.md                           # Project documentation
```

## Quick Start

Choose your preferred setup method:

- **[1. Dev Containers: GitHub Codespaces](#1-dev-containers-github-codespaces)**
- **[2. Direct Install: Local Setup Script](#2-direct-install-local-setup-script)**

## Prerequisites

- **Minimum Disk Space**: 5GB available space
- **Minimum RAM**: 4GB (8GB recommended for optimal performance)
- **Operating System**: Debian (Latest)
- **Network**: Stable internet connection for initial setup / cloud options

## Setup Methods

### 1. Dev Containers: GitHub Codespaces

Use a containerized environment for development with full isolation.

#### Features

- **Containerized**: Isolated development environment
- **Pre-configured**: PHP, Node.js, npm, Composer, and Playwright ready
- **Auto-updates**: Dependencies updated automatically on workspace start
- **VS Code integration**: Built-in extensions and customizations

#### Environment Details

Configured via `.devcontainer/Containerfile`:

- **Base Image**: Debian Slim (Latest) with non-root dev user
- **PHP**: Latest version with comprehensive extensions
- **Node.js**: Official Debian package with npm
- **Additional Tools**: Playwright with browser dependencies, Composer

#### Setup Instructions

1. Fork the repo to your GitHub account
2. Go to your repo → Click **Code** → **Codespaces** → **Create codespace on your desired branch**

**What happens next:** Codespaces auto-detects `.devcontainer` and sets up the environment automatically.

### 2. Direct Install: Local Setup Script

For native system installation without virtualization. This comprehensive setup script installs and configures all necessary development tools on your local system.

#### Features

- **Native performance**: Direct system access without virtualization overhead
- **Full customization**: Complete control over your development environment
- **Offline capable**: Works without internet after initial setup
- **System integration**: Seamless integration with local tools and services
- **Comprehensive tooling**: Includes VS Code, Playwright, and all PHP extensions

#### Environment Details

Configured via `local/local-setup.sh`:

- **System**: Debian (Latest) with root (`sudo`) access
- **PHP**: Latest version with a comprehensive set of common extensions
- **Node.js**: Official Debian package with npm
- **Additional Tools**: Playwright, Composer, VS Code

#### Setup Instructions

```bash
git clone <repo-url>
cd php-javascript-dev-env
sudo bash local/local-setup.sh
```

**Notes:**
- **Prompts**: Prompts for Git user name and email if not already configured.
- **Post-Installation**: Reboot recommended for all changes to take effect.
- **Logs**: Setup logs available at `/var/log/phpjs-dev-environment-setup.log`.

**Warning**: This method modifies your host system directly. Use with caution and ensure you have proper backups.

## Quick Comparison

| Feature | GitHub Codespaces | Local Setup |
|---------|-------------------|-------------|
| **Setup Speed** | Fast | Moderate |
| **Resource Usage** | Container | Native |
| **Internet Required** | Yes | No (after setup) |
| **Customization** | High | Full |
| **Cost** | Free tier | Free |

## Configuration

```bash
# Git configuration (prompted during setup if not set)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global credential.helper "cache --timeout=2592000"
```

## What's Inside?

| Tool                 | Description                                    |
| -------------------- | ---------------------------------------------- |
| **PHP**              | Latest stable version for server-side logic    |
| **Composer**         | PHP dependency manager                         |
| **Node.js & npm**    | Official Debian packages for JavaScript runtime and tooling |
| **Playwright**       | Browser automation and testing framework       |
| **Git**              | Version control system                         |
| **Common Utilities** | `ca-certificates`, `curl`, `gnupg2`, `zip`|
| **VS Code**          | Code editor with Wayland support configured    |

## Getting Started

After setup, create a simple test to verify everything works:

```bash
php -r "echo 'PHP is working!';"
node -e "console.log('Node.js is working!');"
composer --version
npm --version
npx playwright --version
```

## License

Licensed under the MIT License. See [LICENSE](LICENSE).
