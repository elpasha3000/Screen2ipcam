# Screen2ipcam 🎥

**Turn any Windows PC screen into an ONVIF / RTSP IP camera — add it to any NVR, no capture card.**

Screen2ipcam runs on a Windows PC and publishes its screen as a standard **ONVIF Profile S** camera with an **H.264 RTSP** stream (main + sub). Your NVR or VMS discovers it like any other IP camera and records it — no HDMI encoder, no capture hardware.

It's not POS-only: anywhere you'd like a screen visible inside your existing NVR/VMS works — POS terminals, dashboards, a control-room display, digital signage, or keeping an eye on a remote PC.

---

## ✨ Features

- **ONVIF (Profile S)** — auto-discovered by NVRs (WS-Discovery), or add by IP
- **RTSP H.264** streaming — **Main + Sub** streams
- **JPEG snapshot** support (`GetSnapshotUri`)
- **Lightweight** — ~0% CPU idle, ~2% while streaming, ~70 MB RAM
- **Native** C++ with a static runtime — **no .NET, no redistributables**
- Runs on **Windows 7 SP1 → 11**, **32-bit & 64-bit** (Windows IoT / Embedded / POSReady too)
- Installs as a **Windows Service** (always-on) or a tray app
- Three ways to configure: **native GUI**, **web panel**, or a **config file**
- Optional **ONVIF / RTSP authentication** (Digest / WS-Security)
- **Bilingual UI** — Arabic / English

---

## 🖥️ Web control panel

A clean browser-based panel (there's also a native GUI and a plain config file):

**Video — main + sub streams (H.264)**
![Video settings](images/Screenshot%202026-06-07%20170602.jpg)

**Network — ports & optional stream authentication**
![Network settings](images/Screenshot%202026-06-07%20170322.jpg)

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

1. Download the installer below (**x64** or **x86**) and run it.
2. Open the control panel — default login **`admin` / `admin`**.
3. On your NVR: **Add Camera → ONVIF** (auto-discover, or enter the PC's IP + port `8000`).

A one-page **Quick-Start (PDF)** is attached to the release (supported NVRs, ports, and step-by-step for Dahua & Hikvision).

---

## 🗑️ Uninstall

Uninstall from **Settings → Apps**, or the **Uninstall Screen2ipcam** shortcut. It asks for the **program password** (default `admin` / `admin`, or whatever you set) — so a casual user can't remove it from a deployed PC.

Forgot the password? On the web-panel login click **Forgot password?**, then email the Device ID it shows to **ipmagic@aol.com** for a reset code (resets the login to `admin` / `admin`), and uninstall.

---

## 🪪 Status screens (shown on the stream)

| Trial overlay | Stream paused | License screen |
|---|---|---|
| ![Trial](images/trial.png) | ![Paused](images/paused.png) | ![License](images/expired.png) |

---

## 🧪 Public Beta

This is a **free public beta** (3-day trial). Feedback is very welcome — especially:

- NVR / VMS model
- ONVIF discovery result
- Streaming performance & CPU usage
- Anything that didn't work

Targeted / tested with **Dahua**, **Hikvision**, and **Blue Iris**; standard ONVIF/RTSP so enterprise VMS platforms should ingest it fine.

---

## 📬 Contact

📧 **ipmagic@aol.com**  ·  🌐 **github.com/elpasha3000**

---

<sub>⚠️ The binary is native and unsigned, so SmartScreen/Defender may show a warning (false positive). Verify and keep. © MagicWeb.</sub>
