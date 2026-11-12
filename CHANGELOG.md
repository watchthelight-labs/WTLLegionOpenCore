# Changelog

## 2026-11-12

- WTLWireless 0.15.0 in place of 0.14.0 (booted 2026-11-11 on the 26.7.3 developer beta, 25G416). On this laptop's MT7925 nothing changes; the release adds a switched-off MT7927 row. Same three `Kernel > Add` entries, `config.plist` untouched. `MANIFEST.txt` has the new hashes of the kext's six files.

## 2026-11-11

- `EFI/OC/config.plist` refreshed from the live config (it was the one of 2026-10-17). New in it: the three WTLWireless entries in place of MtkWlan and MtkBt, LegionCpuPower, IGPUConsoleRange, the graphical picker (OpenCanopy, `ShowPicker true`, `Timeout 2`, `UIScale 2`), `ScanPolicy 0x301`, two local `Misc > Tools` entries that are not published, and the boot-args `gfxrst=4 -nmintelfboff mtkfe=native mtknativeif=1`. `SSDT-DGPU-ON.aml` and XeGfxBlock are listed but disabled.
- `MANIFEST.txt` regenerated from the EFI partition as it booted on 2026-11-11.
- README and HOW-IT-WORKS follow: kext table in the new load order, picker, drivers and tools.

## 2026-11-10

- README: Wi-Fi and Bluetooth now come from one kext, [WTLWireless](https://github.com/watchthelight-labs/WTLWireless) 0.14.0, with the Wi-Fi menu part and the Bluetooth loader as plugins inside it. It replaced MtkWlan 0.13.0, MtkWlanNative 0.4.17 and MtkBt 0.2.4 on this machine (three `Kernel > Add` entries, the core first). The published `config.plist` is unchanged and still has the older entries.

## 2026-10-27

- `SetApfsTrimTimeout` is 0 now (was -1). APFS no longer trims the free space at mount: the boot scan takes 0 s instead of about 20 s, and the login window comes up 41 s after the root mount instead of 58 s. On macOS 12 and later only 0 (skip) or -1 (default) are honoured.
- README status and kext table brought up to the running versions: Wi-Fi menu through MtkWlan 0.12.1 and MtkWlanNative 0.4.13, MtkBt 0.2.4, LegionCpuProbe 1.1.0, LegionCpuPower 0.4.1, audio through AppleALC `alcid=18`.

## 2026-10-17

- First published state: the EFI and config as they boot macOS Tahoe 26.7.1 and Sequoia 15.8.1 on the Legion 5 15IAX10 (the config that ran boot N-94 of my notebook on 2026-10-17). Includes the shutdown fix (SSDT-FIXSHUTDOWN plus the `_PTS` rename), the four `_UPC` port fixes, the MADT rewrite, the DSDT scope patches, and the kext list for all the drivers in this org.
