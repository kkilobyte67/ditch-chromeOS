## Firmware Method Limitations

| Firmware Method | Windows Support | ChromeOS Support | WP (Write Protect) Requirement | Known Platform Bugs & Quirks |
| :--- | :--- | :--- | :--- | :--- |
| **Full ROM** | Fully Supported | ❌ Unusable | **MUST BE OFF** | Primary audio and trackpad drivers require manual installation post-flash. |
| **AltFw** | ❌ Unsupported | Supported | Can stay **ON** (Requires OFF for GBB flags) | • No touchscreen functionality.<br>• Intel Geminilake: Boot menu layout is visually broken; blind-press `1` at the `Ctrl + L` screen.<br>• AMD Cezanne: Display backlight is broken.<br>• AMD Stoneyridge (`grunt-barla`): Non-functional payload.<br>• Splash screens, UEFI settings, and GRUB menus will appear horizontally stretched. |
| **RW_Legacy** | ❌ Unsupported | Supported | Can stay **ON** | • Broken system suspend functionality observed on `snappy-alan`. <br>• Bootloader environment limited to an 00x600 resolution box in the top-left corner. |
