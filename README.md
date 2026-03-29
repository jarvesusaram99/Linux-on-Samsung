# Run Linux on Samsung

Transform your **Samsung Galaxy** smartphone or tablet into a fully functional, GPU-accelerated **Linux Desktop setup** using Termux! This automated script installs your choice of Desktop Environment (XFCE4, LXQt, MATE, or KDE Plasma), configures Turnip/Zink drivers for Snapdragon hardware acceleration, and gears you up with essential development and security tools.

**Created by**: [Tech Jarves](https://youtube.com/techjarves) – *Subscribe on YouTube for full tutorials!*

## 🚀 Key Features

- **Multiple Desktop Environments**: Choose between and seamlessly switch among XFCE4, LXQt, MATE, and KDE Plasma.
- **Hardware GPU Acceleration**: Automatically configures the Turnip & Zink Vulkan drivers to unlock maximum performance on Snapdragon / Adreno devices (Exynos processors will safely fall back to software rendering).
- **Core Security & Linux Tools**: Metasploit Framework comes pre-installed for authorized security testing.
- **Development Ready**: Python 3, Flask, VS Code (code-oss), and Git are pre-configured out-of-the-box.
- **Windows App Compatibility**: Run `x86_64` Windows applications flawlessly using Wine and Box64 via Hangover.

## 📱 Prerequisites

1. **Samsung Galaxy** device running Android 10 or higher.
2. **Termux**: Download the official version from [F-Droid](https://f-droid.org/en/packages/com.termux/). *(Do not use the Google Play Store version as it is obsolete).*
3. **Termux-X11**: Required to render the Linux display. Download the latest APK from the [Termux-X11 GitHub Releases](https://github.com/termux/termux-x11/releases).
4. **Storage**: Approximately 3-4 GB of free internal space.

## ⚙️ Installation Guide

Choose one of the following methods to install your Linux environment inside Termux.

### Method 1: One-Click Automated Install (Recommended)
Run this single command inside your Termux terminal to fetch and execute the setup:

```bash
apt update && apt upgrade -y && apt install curl -y && curl -fsSL https://raw.githubusercontent.com/jarvesusaram99/Linux-on-Samsung/main/setup-hacklab.sh | bash
```

### Method 2: Manual Clone Setup
Alternatively, if you prefer cloning the repository directly:

```bash
apt update && apt upgrade -y
apt install git curl -y
git clone https://github.com/jarvesusaram99/Linux-on-Samsung.git
cd Linux-on-Samsung
chmod +x setup-hacklab.sh
./setup-hacklab.sh
```

## 🖥️ How to Use Your Linux Desktop

After a successful installation, our smart launcher is placed in your home directory.

1. Keep the **Termux-X11** Android app open in the background.
2. Inside Termux, start your visual desktop with:
   ```bash
   ./start-hacklab.sh
   ```
   *(If you installed multiple desktop environments, you will automatically be prompted to choose which one to boot!)*
3. **Quick Tools Menu**: Access your terminal tools quickly by running: `./hacktools.sh`
4. **Stop the Desktop**: Safely terminate all Linux GUI sessions by running: `./stop-hacklab.sh`

### Testing Your Server Environment (Python Flask)
A lightweight web application is included to verify that your native networking and Python environment are running effectively:
```bash
cd ~/demo_python
python app.py
```
Open your newly installed Firefox Linux browser (or your Android browser) and navigate to `http://localhost:5000` to see your live server!

## ⚡ Performance Matrix & Hardware Compatibility

- **Snapdragon / Adreno GPUs**: This script installs the open-source **Turnip driver**, granting massive hardware acceleration capabilities. Heavy desktop environments like **KDE Plasma** will run exceptionally smooth.
- **Exynos / Mali GPUs**: Exynos architectures are not supported by Turnip; the script will smartly configure a software fallback (llvmpipe). For Exynos users, we heavily recommend selecting **XFCE4** or **LXQt** for optimal battery life and interaction speed.

## ⚠️ Disclaimer 

This script is built for educational IT purposes and authorized security research only. Do not utilize the offensive tools (e.g., Metasploit) incorporated in this package against targets without their explicit, prior permission. The repository creator claims no responsibility for misuse.

---
⭐ **Like this project?** Drop a star on GitHub and subscribe to [Tech Jarves](https://youtube.com/techjarves)!
