# Anycubic Cloud Integration for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/hacs/integration)

---

<a name="english"></a>


### About this Project
This custom integration connects **Anycubic 3D Printers** to Home Assistant using the Anycubic Cloud API. It provides real-time telemetry and control even as local MQTT access becomes more restricted.

### Supported Models
Confirmed working with:
* **Kobra 3 Combo**
* **Kobra 3 Max Combo**
* **Kobra S1**
* **Kobra 2**
* **Kobra 2 Pro**
* **Kobra 2 Max**
* **Photon Mono M5s** (Basic support)
* **M7 Pro** (Basic support)

### Features
- **Printer Sensors:** Temperature (Nozzle/Bed), fan speed, print speed, etc.
- **Job Sensors:** Progress, remaining time, file name, and image previews.
- **Controls:** Start, Pause, Resume, and Cancel print jobs.
- **ACE Pro Features:** Drying management, spool colors, and settings.
- **Sidebar Panel:** Integrated file manager and printer dashboard.

---

## Gallery

<p align="center">
  <img width="300" src="https://raw.githubusercontent.com/WaresWichall/hass-anycubic_cloud/master/screenshots/kobra3-1.png"> 
  <img width="300" src="https://raw.githubusercontent.com/WaresWichall/hass-anycubic_cloud/master/screenshots/anycubic-ace-ui.gif"> 
  <img width="300" src="https://raw.githubusercontent.com/WaresWichall/hass-anycubic_cloud/master/screenshots/kobra2-2.png">
  <br>
  <img width="300" src="https://raw.githubusercontent.com/WaresWichall/hass-anycubic_cloud/master/screenshots/kobra3-print.png"> 
  <img width="200" src="https://raw.githubusercontent.com/WaresWichall/hass-anycubic_cloud/master/screenshots/kobra2-1.png">
</p>

---

## How to Install / Installation

1. **Add Repository:** Add this URL to **HACS** as a "Custom Repository" (Category: Integration).
2. **Install:** Search for "Anycubic Cloud" in HACS and install it.
3. **Restart:** Restart Home Assistant.
4. **Setup:** Go to Settings > Devices & Services > Add Integration > **Anycubic Cloud**.

### Authentication Methods

#### 1. Slicer Next (Recommended for Kobra 3 / S1 / Kobra 2 Series)
1. Open `%AppData%\AnycubicSlicerNext\AnycubicSlicerNext.conf` (Windows) or `~/Library/Application Support/AnycubicSlicerNext/AnycubicSlicerNext.conf` (macOS).
2. Copy the long `access_token` string.
3. Paste it into the Home Assistant config flow.

#### 2. Web Authentication
1. Log in to [Anycubic Cloud Web](https://cloud-universe.anycubic.com/file).
2. Open Browser Dev Tools (F12) -> Console.
3. Type `window.localStorage["XX-Token"]` and copy the result.

---

### Technical Components / Technische Komponenten
* `manifest.json`: Metadata, 2026 compatibility, and dependencies.
* `sensor.py`: Core logic for creating and updating entities.
* `api.py`: Communication with Anycubic's Cloud Universe.
* `panel.js`: Frontend logic for the sidebar file manager.

### Thanks / Danke
Special thanks to **@WaresWichall** for the original cloud integration and **@dangreco** for the initial foundation.
