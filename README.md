# QEMU Android PC Emulator x86_64 Emulator for Android (Termux)

This project provides a ready-to-run **x86_64 desktop emulator**
using **QEMU on Android via Termux**.



It includes:
- EFI (OVMF)
- Working sound
- Working internet
- VNC graphical desktop

⚠️ Disk images (ISO / QCOW2) are NOT included for legal and size reasons.

---

## Requirements

- Android device (ARM64 recommended)
- Termux (from F-Droid)
- QEMU installed in Termux
- VNC Viewer app (e.g. RealVNC, bVNC)

---

## Installation

### 1. Install required packages in Termux

```bash
pkg update
pkg install qemu-utils qemu-system-x86_64 wget unzip


2. Download this repository
Option A: Download ZIP from GitHub and extract it
Option B: Clone the repository
Code kopieren
Bash
git clone https://github.com/YOUR_USERNAME/qemu-android-debian.git
cd qemu-android-debian
Disk Image Setup (Required)
3. Download Debian 12 ISO
Example (netinst):
Code kopieren
Bash
wget https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.5.0-amd64-netinst.iso
Move it into the images/ folder.
4. Create a QCOW2 disk image
Code kopieren
Bash
qemu-img create -f qcow2 images/debian12.qcow2 20G
First Boot / Installation
5. Start the emulator with ISO
Code kopieren
Bash
./start-debian.sh
The emulator will start and open a VNC server at:
Code kopieren

127.0.0.1:5900
6. Connect with a VNC Viewer
Open your VNC app
Connect to:
Code kopieren

127.0.0.1:5900
Follow the Debian installer
Install GRUB when asked
Use EFI (default)
Normal Boot (After Installation)
After Debian is installed, remove or rename the ISO:
Code kopieren
Bash
mv images/debian-12*.iso images/debian.iso.bak
Then start again:
Code kopieren
Bash
./start-debian.sh
Debian will now boot directly from the disk image.
Controls & Notes
This is full x86_64 emulation, not virtualization
Performance depends on your device
Recommended RAM: 4 GB
Desktop environments should be lightweight (LXDE, XFCE)
Troubleshooting
Black screen?
Wait 1–2 minutes (slow boot is normal)
Check VNC connection
Very slow performance?
Reduce desktop effects
Use lighter desktop environment
Disclaimer
This project is for educational and experimental purposes. No operating system images are distributed with this repository.
License
Open-source, provided as-is.
Code kopieren

---

