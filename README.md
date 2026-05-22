# Bin-r-Uhr
Selfmade Binary Clock

Flashen in VS Code:

PlatformIO → Upload
oder Terminal:
pio run -t clean
pio run -t upload

------------------------------------------------

You can open it in VS Code + PlatformIO and flash it normally using Upload.

Flashing in VS Code:

PlatformIO → Upload
or via terminal:
pio run -t clean
pio run -t upload
------------------------------------------------------------------------------------------------
* **Binary time display**

  * Hours shown as a **5-bit LED row**
  * Minutes shown as a **6-bit LED row**
* **“Analog” seconds display**

  * Seconds as a **PWM output** (e.g., voltmeter/needle), with smooth movement
* **Automatic brightness**

  * **Light sensor (ADC)** measures ambient light
  * LED brightness is adjusted automatically (filtered to prevent flicker)
* **Backlight control**

  * Backlight via PWM
  * On/off with **hysteresis** for stable behavior
* **Real-Time Clock (RTC DS3231)**

  * RTC can be enabled/disabled
  * RTC → system time on boot (fallback)
  * After successful NTP: system time → RTC writeback
  * Manual RTC time setting via the web UI (depending on your current UI build)
* **NTP time synchronization**

  * **Immediately after boot** if WiFi is available
  * Then periodically (typically every **6 hours**)
  * **Multiple NTP servers** with fallback + retry logic
* **WiFi modes**

  * **STA mode** (connects to saved WiFi)
  * **AP setup mode** via button (Access Point + captive portal)
  * WiFi can be turned **off after sync** to save power
* **Web interface (captive-portal capable)**

  * Tabs: **Home**, **WiFi**, **Log**
  * Home: status (time/sync/WiFi/RTC), optional “sync now”
  * WiFi: set SSID/password, **scan**, select network, reconnect, forget network
  * Log: view event/debug log in the browser
* **Logging**

  * Event log for NTP/RTC/WiFi/AP/scan etc., viewable via the web UI
