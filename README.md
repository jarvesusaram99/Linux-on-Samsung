# Samsung Mobile HackLab

A script to convert your Samsung Galaxy device into a Linux desktop environment within Termux. It installs your choice of desktop, configures GPU acceleration (optimizing for Snapdragon/Adreno), and sets up essential development and security tools.

**Created by**: [Tech Jarves](https://youtube.com/techjarves)

## Features

- **Desktop Environments**: Choose between XFCE4, LXQt, MATE, or KDE Plasma.
- **Hardware Acceleration**: Automatically configures Turnip/Zink for Snapdragon devices (Exynos devices fall back to software rendering).
- **Core Tools Installed**:
  - **Security**: Metasploit Framework
  - **Development**: Python 3, Flask, VS Code (code-oss), Git
  - **Internet & Media**: Firefox, VLC Player 
  - **Windows Compatibility**: Wine and Box64 via Hangover

## Prerequisites

1. **Samsung Galaxy** device (Android 10+)
2. **Termux**: Must be installed from [F-Droid](https://f-droid.org/en/packages/com.termux/), not the Google Play Store (the Play Store version is obsolete).
3. **Termux-X11**: Required to display the desktop environment. Install the APK from their [GitHub Releases](https://github.com/termux/termux-x11/releases).
4. Approx. 3-4 GB of free storage.

## Installation

Run this single command inside your Termux terminal:

```bash
apt update && apt upgrade -y && apt install curl -y && curl -fsSL https://raw.githubusercontent.com/jarvesusaram99/Linux-on-Samsung/main/setup-hacklab.sh | bash
```

Alternatively, you can clone the repository and run it manually:

```bash
apt update && apt upgrade -y
apt install git curl -y
git clone https://github.com/jarvesusaram99/Linux-on-Samsung.git
cd Linux-on-Samsung
chmod +x setup-hacklab.sh
./setup-hacklab.sh
```

## Usage

After installation, the script creates helper shortcuts in your home directory:

- **Start the Desktop**: `./start-hacklab.sh` (Make sure the Termux-X11 app is open)
- **Open Quick Tools Menu**: `./hacktools.sh`
- **Stop the Desktop**: `./stop-hacklab.sh`

### Running the Python Demo
A sample Flask application is included to test your environment:
```bash
cd ~/demo_python
python app.py
```
Then navigate to `http://localhost:5000` in your Termux Firefox browser.

## Notes on Performance

- **Snapdragon Devices**: The script installs the Turnip driver which provides hardware acceleration for Adreno GPUs. This allows heavier desktop environments like KDE to run reasonably well.
- **Exynos Devices**: Exynos processors use Mali GPUs, which are not currently supported by Turnip. The script will configure a software fallback. For these devices, it is highly recommended to select **XFCE4** or **LXQt** during installation to maintain good performance.

## Disclaimer 

This script is provided for educational purposes and authorized security research only. Do not use the installed tools against targets without explicit permission. The author is not responsible for any misuse.
