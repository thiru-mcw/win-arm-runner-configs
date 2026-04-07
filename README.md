# 🖥️ Win-11-ARM GH_Runner Deep System Info

This repository provides a **GitHub Actions workflow** to extract **deep system-level information** from a **Windows 11 ARM runner**, including CPU capabilities, hardware details, OS configuration, and runtime support.

---

## 🚀 Features

* 🧠 **CPU Inspection**

  * Core / thread count
  * Cache details
  * ARM architecture info

* ⚡ **ARM Capability Detection**

  * NEON (AdvSIMD)
  * AES / SHA / CRC instructions
  * ARMv8+ feature flags

* ⚙️ **Windows Low-Level Features**

  * `IsProcessorFeaturePresent` checks
  * Kernel-exposed CPU capabilities

* 💻 **System Information**

  * OS version & build
  * BIOS / firmware
  * Memory & storage

* 🌐 **Network Details**

  * Adapter configuration
  * Full `ipconfig` output

* 🧬 **Runtime & Environment**

  * .NET runtime info
  * Environment variables

* 📦 **Artifacts**

  * System reports saved and uploaded from each run

---

## 📂 Workflow

The workflow is located at:

```
.github/workflows/config.yaml
.github/workflows/deep_config.yaml
```

It runs on:

```
windows-11-arm
```

---

## ▶️ Usage

### Trigger manually:

* Go to **Actions tab**
* Select workflow
* Click **Run workflow**

### Or trigger via push:

```bash
git push
```

---

## 📊 Output

The workflow prints detailed logs and uploads artifacts:

* `systeminfo.txt`
* `computerinfo.txt`

These contain full system snapshots for analysis.

---

## 🧠 Notes

* Windows does not expose ARM features as fully as Linux (`/proc/cpuinfo`)
* This workflow uses:

  * .NET intrinsics (most reliable)
  * Windows API (`kernel32.dll`)
* For deeper hardware flags (e.g., SVE), consider adding WSL:

```yaml
- run: wsl cat /proc/cpuinfo
```

---

## 📜 License

MIT License

---

## 🤝 Contributing

PRs and suggestions are welcome!
