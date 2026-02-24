# Dual Audio Manager

![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-Linux-blue)
![Shell](https://img.shields.io/badge/language-Bash-orange)
![PipeWire](https://img.shields.io/badge/audio-PipeWire%20%7C%20PulseAudio-purple)

A lightweight CLI tool to manage **single, dual, and multi audio outputs** on Linux.

Supports:
- AUX (3.5mm)
- USB audio devices
- Bluetooth headsets
- HDMI
- Any PipeWire / PulseAudio sink

---

## Features

- Arrow-key interactive menu (fzf powered)
- Combine 2 or more audio outputs
- Multi-device support
- Quick remove shortcut (`-r`)
- No permanent system configuration changes
- Works with PipeWire and PulseAudio

---

# System Requirements

- Linux (Ubuntu, Debian, Arch, Fedora, Mint, Pop!_OS, etc.)
- PipeWire **or** PulseAudio
- `pactl`
- `fzf`
- `git` (for installation via clone)

Check compatibility:

```bash
pactl info
```

If this command works, the tool will work.

---

# Full Installation Guide (From Git to Usage)

## 1️⃣ Install Required Dependencies

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install git fzf
```

### Arch Linux

```bash
sudo pacman -S git fzf
```

### Fedora

```bash
sudo dnf install git fzf
```

---

## 2️⃣ Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/dual-audio-manager.git
cd dual-audio-manager
```

---

## 3️⃣ Install the Tool

Make the installer executable:

```bash
chmod +x install.sh
```

Run the installer:

```bash
./install.sh
```

This installs the script to:

```
/usr/local/bin/dual-audio
```

Now the command `dual-audio` will work system-wide.

---

## 4️⃣ Verify Installation

Run:

```bash
dual-audio
```

If the arrow-key menu appears, installation is successful.

---

# Manual Installation (Alternative)

If you prefer manual setup:

```bash
sudo cp dual-audio /usr/local/bin/
sudo chmod +x /usr/local/bin/dual-audio
```

---

# Updating the Tool

To update:

```bash
cd dual-audio-manager
git pull
./install.sh
```

---

# Uninstall

If installed using installer:

```bash
./uninstall.sh
```

Or manually:

```bash
sudo rm -f /usr/local/bin/dual-audio
```

---

# Usage

## Interactive Mode (Arrow Keys)

```bash
dual-audio
```

Use:
- ↑ ↓ arrows to navigate
- Enter to select
- TAB to select multiple devices

---

## Remove Combined Sink Instantly

```bash
dual-audio -r
```

---

# How It Works

- Uses `pactl` to detect audio sinks
- Uses `module-combine-sink` to merge outputs
- Uses `fzf` for interactive UI
- Does not modify system audio configuration permanently

All changes are session-based.

---

# Troubleshooting

## No Sound After Combining

Reset:

```bash
dual-audio -r
```

Then reselect your output.

---

## Device Not Appearing

Check available sinks:

```bash
pactl list short sinks
```

If your device does not appear, it is not detected by the system.

---

# Compatibility

| Platform | Supported |
|----------|------------|
| Linux (PipeWire) | ✅ Yes |
| Linux (PulseAudio) | ✅ Yes |
| macOS | ❌ No |
| Windows | ❌ No |

---

# License

MIT License

---

# Author

Sudhanshu Thapa
GitHub: https://github.com/Sudhanshu943/dual-audio-manager.git
