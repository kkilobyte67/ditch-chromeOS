# Unenrollment for Chrome OS Devices
Useful for ditching ChromeOS and using Full ROM, AltFw, or RW_Legacy methods.
Note: You can always use the Shim method for Linux without unenrollment!

## Table of Contents
- [Unenrollment](#unenrollment-for-chrome-os-devices)
  * [Why unenroll?](#why-unenroll-)
  * [What Kernver and ChromeOS version do I have?](#what-kernver-and-chromeos-version-do-i-have-)
- [Kernver to ChromeOS Table](#kernver--kv--to-chromeos--cros--table)
- [How do I unenroll?](#how-do-i-unenroll-)
  * [SHroot](#chromeos-v101-and-below---shroot)
  * [SH1mmer](#chromeos-v110-and-below---sh1mmer)
  * [CryptoSmite](#chromeos-v118-and-below---cryptosmite)
  * [BadRecovery](#chromeos-v124-and-below---badrecovery--formerly-olybmmer-------i-have-no-idea-how-accurate-this-guide-is-going-to-be-because-i-have-never-used-badrecovery-before----)
  * [icarus](##chromeos-v129-and-below---icarus)
  * [BadApple+Icarus]()
  * [CRSH2TTY](#crsh2tty--all-versions--patched-)

 <small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

## Why unenroll?
Every method except the Shim method requires FWMP to be missing as Developer Mode is required, but FWMP blocks Developer Mode. Thus we need to remove FWMP. 

## What Kernver and ChromeOS version do I have?
To verify your kernver and your ChromeOS version, you need to first boot ChromeOS and then press `alt+v`, you will find a number followed by other numbers, only the first 2 or 3 numbers matter, such as `94`, `110` or `127`. Take note of this number and find the method related. If it is `120` or higher, you should check your kernver. Press `esc+⟳+⏻ ` (`esc+refresh+power`), and then `tab`. 

Now, you just scroll down with your eyes until you find `tpm_ver`, and then look to the right of that to find `tpm_kernver`, and your kernver will be the last number to the right of kernver, this means `tpm_kernver=0x00010004` is kernver 4 or kv4.

# Kernver (kv) to ChromeOS (crOS) table
Please note this can be inaccurate because kernver skipping (aka kernskip) is really common. For example, I own an `octopus-phaser360` Chromebook with kernver 1 but on ChromeOS v126 (v126 is kernver 4), and many people got ChromeOS v113 on kernver 1 (v113 is kernver 2).
In the event of a kernskip, you should downgrade to the versions connected to your kernver to be allowed access to more exploits.

| Kernver   | ChromeOS version            | Unenroll method |
|-----------|-----------------------------|---------------|
| 0<sup>1</sup> | any up to v111<sup>3</sup> | SHroot (to v101) or SH1mmer (to v110) |
| 1 | any up to v111<sup>3</sup> | SHroot (to v101) or SH1mmer (to v110) |
| 2<sup>2</sup> | v112 to v119<sup>4</sup>| Cryptosmite (to v118) |
| 3 | v120 to v125<sup>5</sup> | BadRecovery |
| 4 | v126 to v131 | icarus (to v129) / br1ck (to v130) / BadApple (to v131) |
| 5 | v132+ | CRSH2TTY (patched) |

<sub><sup>Kv0 is usually a factory setting bug<sup>1</sup></sup></sub> \
<sub><sup>On some devices, kv2 is actually crOS v111<sup>2</sup></sup></sub> \
<sub><sup>v110 or lower recommended<sup>3</sup></sup></sub> \
<sub><sup>v118 or lower recommended<sup>4</sup></sup></sub> \
<sub><sup>Some early versions of v120 is kv2, however newer versions are kv3<sup>5</sup></sup></sub> \
<sub><sup>Some early versions of v125 is kv3, however newer versions are kv4<sup>5</sup></sup></sub> \
<sub><sup>v124 or lower recommended<sup>5</sup></sup></sub>

# How do I unenroll?
## ChromeOS v101 and below - SHroot
