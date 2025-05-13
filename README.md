# LXQt LY Login Manager Switch

[![Release](https://img.shields.io/github/v/release/SpeedyCoder1192/legacysupport-archlinux)](https://github.com/SpeedyCoder1192/legacysupport-archlinux/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A simple script to replace SDDM with [LY](https://github.com/nullgemm/ly) on **LXQt-based Ubuntu systems**, and configure LXQt to auto-start after login via TTY.

LY is a lightweight, terminal-based login manager — perfect for minimal setups or users who prefer keyboard-driven workflows.

---

## ✅ Features

- Removes SDDM
- Installs LY from source
- Enables LY as the default login manager
- Configures LXQt to start automatically on login
- Compatible with Ubuntu 24.04 and derivatives using LXQt

---

## 📦 Supported Systems

This script is designed for LXQt-based systems using `systemd`.

| Distribution                 | Supported? | Notes                                                         |
|------------------------------|------------|---------------------------------------------------------------|
| **Lubuntu 24.04**            | ✅ Yes      | Official LXQt-based Ubuntu flavor                             |
| **Ubuntu Minimal + LXQt**    | ✅ Yes      | Works if LXQt is installed manually                           |
| **Kubuntu/Xubuntu + LXQt**   | ✅ Yes      | Safe if LXQt is your primary desktop                          |
| **Debian LXQt**              | ⚠️ Probably | Probably works, but not tested                                |
| **Arch/Manjaro LXQt**        | ❌ No       | Use a Pacman-based variant of the script                      |

---

## 🚀 Usage

Run the following commands:

```bash
git clone https://github.com/yourusername/lxqt-ly-switch.git
cd lxqt-ly-switch
chmod +x switch-to-ly-lxqt.sh
./switch-to-ly-lxqt.sh
```

After the script finishes, reboot to start using LY:

```bash
sudo reboot
```

---

## ⚙️ What the Script Does

1. Disables and removes SDDM.
2. Installs build tools and dependencies for LY.
3. Clones and builds LY from source.
4. Enables the `ly.service` with systemd.
5. Adds a `.bash_profile` or `.zprofile` script that launches `startlxqt` on login.

This ensures that after logging in through LY, your LXQt session starts automatically.

---

## 📝 Notes

- LY is a **keyboard-only** login manager. Mouse input is not supported.
- If `.bash_profile` exists, it is modified. Otherwise `.zprofile` is used.
- The script assumes the user logging in via LY will use TTY1.
- Debian systems: Probably works, but not tested.

---

## 🧾 License

This project is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).
