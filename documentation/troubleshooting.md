# 1> Troubleshooting

If something has gone wrong, work through the basics first.

**Power.** Underpowered supplies often cause flaky behaviour. Power the Pi1551-III from the **Raspberry Pi’s USB Micro** port with a good **5 V, at least 2 A** supply. Cheap adapters can fail or damage the Pi over time; use a known-good PSU.

**Display.** If the OLED is completely dark, take the Pi out and start it with HDMI connected to a monitor. Black or rainbow screen? Check the SD card — any difference with the card in or out? Many cards ship as **exFAT**; the Pi boots only from **FAT32**. Format the card with [fat32format](http://ridgecrop.co.uk/index.htm?guiformat.htm) or the [SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter/) (do not format the wrong drive).

**OLED still dark** after that? Check **JP3/JP4** on the [Pi1551-III Module Panel](../Pi1551-III%20Module%20Panel) — they set the OLED’s VCC/GND pin order for your SH1106 module. Match them to your display’s pinout. If you had them wrong and already powered up, the display may be damaged (replace it). **Graphical glitches** usually mean the display is configured as *ssd1306* in options; most 1.3" modules are actually **sh1106** — set the display type to sh1106 in the [Pi1551](https://github.com/ytmytm/Pi1551) configuration.

**Firmware and configuration.** SD card layout, options, and behaviour are documented in the **[Pi1551](https://github.com/ytmytm/Pi1551)** project on GitHub. For loading issues, config, or TAP, check that project’s docs and issues.

**Quick test.** Once the device runs, pick a D64 from the SD card and start emulation. On the Commodore 16, C116 or Plus/4, try:
```
DIRECTORY
```
to confirm the 1551 is responding.
