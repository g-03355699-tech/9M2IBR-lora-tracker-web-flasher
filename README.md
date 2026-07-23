# 9M2IBR LoRa APRS Tracker — Web Flasher

Browser-based firmware installer for the **9M2IBR LoRa APRS Tracker** (a personal fork of the CA2RXU LoRa APRS Tracker). Flash a board straight from Chrome or Edge over USB — no PlatformIO, no IDE, no drivers beyond the standard ESP32 USB-serial driver.

**Flash here:** https://g-03355699-tech.github.io/9M2IBR-lora-tracker-web-flasher/installer.html

## How to use

1. Open the link above in **Google Chrome** or **Microsoft Edge** (this needs the [Web Serial API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Serial_API) — other browsers aren't supported).
2. Pick your **board variant** and **firmware version** from the dropdowns.
3. Plug the tracker in over USB, click **Flash Firmware**, and select the matching serial port when prompted.
4. This writes bootloader + partitions + app + filesystem in one pass (`web_factory.bin`) — a first flash or full factory reset. Existing on-device configuration (SPIFFS) is erased; reconfigure via the tracker's own WiFi AP afterwards.

## What lives in this repo

This site is powered by [ESP Web Tools](https://esphome.github.io/esp-web-tools/) and generated/published automatically by CI in the firmware repo — nothing here is meant to be hand-edited:

- `installer.html`, `index.html` — synced from the firmware repo's `webflasher/` folder on every release.
- `bins/<version>/<board>/web_factory.bin`, `manifests/<version>/<board>/factory.json`, `versions.json` — generated fresh from each GitHub Release build; accumulate across versions.

## Source

Firmware source (private repo, maintained by 9M2IBR): `9M2IBR-LoRa-APRS-Tracker`.
