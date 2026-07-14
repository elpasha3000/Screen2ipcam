# Screen2ipcam 🎥

**Turn any Windows PC screen, window or webcam into a standard ONVIF / RTSP IP camera — record it in any NVR or VMS, with no capture card and no hardware encoder.**

<p align="center">
  <img src="https://img.shields.io/badge/Windows-7%20SP1%20%E2%86%92%2011-0078D6?logo=windows" alt="Windows 7 SP1 to 11">
  <img src="https://img.shields.io/badge/ONVIF%20%2F%20RTSP-H.264-16a34a" alt="ONVIF / RTSP">
  <img src="https://img.shields.io/badge/Microsoft%20Store-signed-0078D6?logo=microsoftstore" alt="On the Microsoft Store, signed">
  <img src="https://img.shields.io/badge/Free%20trial-14%20days-16a34a" alt="Free 14-day trial">
</p>

<p align="center">
  <img src="images/hero.png" alt="A Windows PC screen shown live as a camera inside an NVR/VMS grid, alongside real CCTV cameras" width="100%">
</p>

<p align="center"><i>A Windows PC screen — live in your NVR, right next to your real cameras.</i></p>

Screen2ipcam runs on a Windows PC and publishes its **screen, a single window, or a webcam** as a standard **ONVIF Profile S** camera with an **H.264 RTSP** stream (main + sub). Your NVR or VMS — **Dahua, Hikvision, Milestone, Genetec, Nx Witness, Blue Iris** — discovers it like any other IP camera and records it. No HDMI encoder, no capture hardware.

It's not POS-only: anywhere you'd like a screen visible inside your existing NVR/VMS works — POS terminals, dashboards, a control-room display, digital signage, or keeping an eye on a remote PC.

🌐 **Official site: [magicweb.win](https://magicweb.win)**

---

## ⬇️ Download — free 14-day trial

**Easiest, zero-warning install** — the free edition on the **Microsoft Store** is signed by Microsoft, so there's no SmartScreen/Defender warning:

> ### 🏬 [**Get it from the Microsoft Store →**](https://apps.microsoft.com/detail/9pjdgr30l9l1?cid=github)

**Or grab the installer directly:**

| Download | |
|---|---|
| 🌐 **Official site — all options** | **[magicweb.win](https://magicweb.win/#download)** |
| 💾 **64-bit** (modern PCs) | [Screen2ipcam_Setup_1.1.0_x64.exe](https://sourceforge.net/projects/screen2ipcam/files/windows-v1.1.0/Screen2ipcam_Setup_1.1.0_x64.exe/download) |
| 🖥️ **32-bit** (older / embedded / POS) | [Screen2ipcam_Setup_1.1.0_x86.exe](https://sourceforge.net/projects/screen2ipcam/files/windows-v1.1.0/Screen2ipcam_Setup_1.1.0_x86.exe/download) |
| 📘 **User guide (EN)** | [Screen2ipcam_Guide_EN.pdf](https://sourceforge.net/projects/screen2ipcam/files/windows-v1.1.0/Screen2ipcam_Guide_EN.pdf/download) |
| 📗 **دليل الاستخدام (AR)** | [Screen2ipcam_Guide_AR.pdf](https://sourceforge.net/projects/screen2ipcam/files/windows-v1.1.0/Screen2ipcam_Guide_AR.pdf/download) |

The trial is **14 days, fully functional**. A one-time license unlocks the full version — **no watermark, no time limit**.

---

## ✨ Features

- **ONVIF (Profile S)** — auto-discovered by NVRs (WS-Discovery), or add by IP
- **RTSP H.264** streaming — **Main + Sub** streams
- Capture a **full screen, a single window, or a webcam**
- **JPEG snapshot** support (`GetSnapshotUri`)
- **Lightweight** — ~0% CPU idle, ~2% while streaming, ~70 MB RAM
- **Native** C++ with a static runtime — **no .NET, no redistributables**
- Runs on **Windows 7 SP1 → 11**, **32-bit & 64-bit** (Windows IoT / Embedded / POSReady too)
- Installs as a **Windows Service** (always-on) or a tray app
- Three ways to configure: **native GUI**, **web panel**, or a **config file**
- Optional **ONVIF / RTSP authentication** (Digest / WS-Security)
- **Bilingual UI** — Arabic / English

---

## 💲 Pricing

- **Free 14-day trial** — every feature unlocked.
- **Lifetime license — $20, one-time** — removes the watermark and the time limit, forever. Each license activates **one PC**, locked to its Device ID.

See **[magicweb.win](https://magicweb.win/#pricing)** for details and to buy.

---

## 🎯 Use cases

Anywhere there's an important screen you'd like to turn into an IP camera inside your existing surveillance system:

- 🧾 **POS & cashier systems** — review a transaction next to the matching camera video.
- 🏫 **Schools & training centers** — supervise or record lab / lecture / training screens.
- 🏭 **Factories & production lines** — keep SCADA / HMI / line screens on the same recorder.
- 🚚 **Warehouses & logistics** — capture WMS / dispatch screens alongside site cameras.
- 🏥 **Healthcare facilities & labs** — record approved equipment / monitoring screens.
- 🎓 **Examination & accreditation centers** — supervise exam workstations.
- 🏢 **Remote branches & sites** — keep an eye on a screen through the system you already use for cameras.

Software-only and standard **ONVIF / RTSP** — it drops into your existing NVR/VMS like any IP camera. No HDMI encoder, no capture card.

> Used responsibly and lawfully — see the License Agreement. The operator is solely responsible for obtaining any required consents.

---

## 🖥️ Web control panel

Browser-based panel at `http://[device-ip]:8080`:

**System / License** — device ID, license status, and activation QR
![System / License](images/panel-system.png)

**Network** — ports & optional stream authentication
![Network](images/Screenshot%202026-06-07%20170322.jpg)

---

## 🪟 Windows control panel

A native desktop app (runs in the system tray) — plus an installer that can set it up as an always-on Windows service:

**Desktop control panel** — stream settings, tray icon, and service status
![Windows control panel](images/win-panel.png)

**Installer** — desktop shortcut, run at startup, and install as a Windows service
![Installer tasks](images/win-installer.png)

---

## 🔌 How it works

```
PC screen  →  H.264 encode  →  ONVIF / RTSP  →  your NVR / VMS
```

**Ports**

| Port | Protocol | Purpose |
|---|---|---|
| 554  | TCP | RTSP stream |
| 8000 | TCP | ONVIF service |
| 8080 | TCP | Web admin panel (not needed by the NVR) |
| 3702 | UDP | WS-Discovery (optional — you can add by IP instead) |

For a segmented camera VLAN, the NVR only needs to reach the PC on **554** and **8000**.

---

## 🚀 Quick start

1. Install from the **[Microsoft Store](https://apps.microsoft.com/detail/9pjdgr30l9l1?cid=github)** (signed) or download the installer above and run it.
2. Open the control panel — default login **`admin` / `admin`**.
3. On your NVR: **Add Camera → ONVIF** (auto-discover, or enter the PC's IP + port `8000`).

A step-by-step **user guide (PDF)** — supported NVRs, ports, and setup for Dahua & Hikvision — is available in [English](https://sourceforge.net/projects/screen2ipcam/files/windows-v1.1.0/Screen2ipcam_Guide_EN.pdf/download) and [Arabic](https://sourceforge.net/projects/screen2ipcam/files/windows-v1.1.0/Screen2ipcam_Guide_AR.pdf/download).

---

## 🗑️ Uninstall

Uninstall from **Settings → Apps**, or the **Uninstall Screen2ipcam** shortcut. It asks for the **program password** (default `admin` / `admin`, or whatever you set) — so a casual user can't remove it from a deployed PC.

Forgot the password? On the web-panel login click **Forgot password?**, then email the Device ID it shows to **support@magicweb.win** for a reset code (resets the login to `admin` / `admin`), and uninstall.

---

## 🖼️ See it in action

<p align="center">
  <img src="images/screen2ipcam.png" alt="Screen2ipcam — turn any PC screen into an ONVIF / RTSP IP camera, recorded in an NVR right next to real cameras" width="100%">
</p>

<p align="center">
  <img src="images/howit_v1_badged.png" alt="How Screen2ipcam works: 1) any Windows screen, 2) Screen2ipcam turns it into a standard ONVIF / RTSP IP camera (signed on the Microsoft Store), 3) your NVR records it like any camera" width="100%">
</p>

<p align="center">
  <img src="images/how-it-works.png" alt="Screen2ipcam overview — Windows screen to ONVIF / RTSP, works with Hikvision, Dahua, Blue Iris; use cases: POS, dashboards, hospitals, factories, control rooms, digital signage" width="100%">
</p>

<p align="center">
  <img src="images/devices.png" alt="View your Screen2ipcam stream on any device — PC, Android, iPhone / iPad, Smart TV, NVR / DVR, web browser, Raspberry Pi (RTSP 554 · ONVIF 8000 · Web 8080)" width="66%">
</p>

---

## ⭐ Reviewed by Softpedia

<p align="center">
  <a href="https://www.softpedia.com/get/Internet/Streaming/Screen2ipcam.shtml"><img src="https://img.shields.io/badge/Softpedia-100%25%20CLEAN%20%C2%B7%20Certified-16a34a" alt="Softpedia — 100% Clean, Certified"></a>
  <img src="https://img.shields.io/badge/Rating-5.0%20%2F%205-f59e0b" alt="Softpedia rating 5.0 out of 5">
  <img src="https://img.shields.io/badge/Reviewed%20by-Robert%20Condorache-1b4fd6" alt="Reviewed by Robert Condorache">
</p>

> **Screen2ipcam essentially turns your computer into an IP camera.** Your computer is then recognized as such by your NVR, enabling you to monitor your security footage and computer screen from the same place, with the program facilitating this workflow through a straightforward setup process.
>
> **Stream your screen like an IP camera** — "Although turning your computer screen into an IP camera sounds like a complicated thing to do, that's not the case here. The software makes the whole process easy to go through, so you should be able to stream your screen within minutes of setting up the app. The connection to your surveillance device is handled via ONVIF … you can always input the RTSP address into VLC or a compatible player to check if the stream is active."
>
> **Comes with several options for customization** — "The program uses H.264 as the main codec, with options for tweaking resolution, frame rate, and bit rate … you can also opt for different RTSP and ONVIF ports from the app or web portal."
>
> — **Robert Condorache** · [Softpedia review](https://www.softpedia.com/get/Internet/Streaming/Screen2ipcam.shtml) · rated **5.0 / 5** · **Certified 100% Clean**

**Screenshots from the review:**

|  |  |  |
|:--:|:--:|:--:|
| ![Web panel — Live view and stream URLs](images/softpedia-web-live.png) | ![Web panel — Video and stream settings](images/softpedia-web-video.png) | ![Web panel — Network and ports](images/softpedia-web-network.png) |
| **Web panel · Live** | **Web panel · Video** | **Web panel · Network** |
| ![Desktop app — Video settings](images/softpedia-native-video.png) | ![Desktop app — Network settings](images/softpedia-native-network.png) | ![RTSP stream verified in VLC](images/softpedia-vlc.png) |
| **Desktop app · Video** | **Desktop app · Network** | **Verified in VLC (RTSP)** |

---

## 📚 Also listed on

Screen2ipcam is indexed on independent software directories:

- [Softpedia](https://www.softpedia.com/get/Internet/Streaming/Screen2ipcam.shtml)
- [Soft112](https://screen2ipcam.soft112.com/)
- [Software Informer](https://screen2ipcam.software.informer.com/)

---

## 💬 Feedback

Feedback is very welcome — especially:

- NVR / VMS model
- ONVIF discovery result
- Streaming performance & CPU usage
- Anything that didn't work

Targeted / tested with **Dahua**, **Hikvision**, and **Blue Iris**; standard ONVIF/RTSP so enterprise VMS platforms should ingest it fine.

Share feedback in the **[Discussions](https://github.com/elpasha3000/Screen2ipcam/discussions)** tab, or open an **[Issue](https://github.com/elpasha3000/Screen2ipcam/issues)**.

---

## 📬 Contact

📧 **support@magicweb.win**  ·  🌐 **[magicweb.win](https://magicweb.win)**

---

<sub>💡 The direct installer is native and not code-signed yet, so SmartScreen/Defender may show a warning (false positive) — it's safe to keep. For a zero-warning install, use the **Microsoft Store** edition, which is signed by Microsoft. © MagicWeb.</sub>
