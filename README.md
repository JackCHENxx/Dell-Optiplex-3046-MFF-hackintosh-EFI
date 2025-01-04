# Dell-Optiplex-3046-MFF-hackintosh-EFI

Modified from: https://bbs.pcbeta.com/viewthread-1883242-1-1.html

Tested on: macOS Catalina&Big Sur with Opencore: 0.7.6

## Dell Optiplex 3046 SFF hardware configration:

CPU: Skylake-S Core I5 - 6500T

GPU: Intel(R) HD Graphics 530

RAM: 2* 8 GB DDR4- 2133

Audio card: Realtek ALC255 @ Intel Sunrise Point PCH

Ethernet: Realtek RTL8168/8111

Wifi&Bluetooth: [Intel(R) Dual Band Wireless AC 8260 with Blutooth 4.2](https://ark.intel.com/content/www/us/en/ark/products/86068/intel-dual-band-wirelessac-8260.html)



## Installation instruction:

1. Bios setting:
   - [x] Resert to default
   - [x] setting -> general -> Boot Sequence -> Boot List Option -> UEFI
   - [x] setting -> general -> Advanced Boot Options -> **UNCHECK** Enable legacy Option ROMS
   - [x] setting -> video -> promary display -> Intel HD Graphics
   - [x] setting -> secure boot -> secure boot enalbe -> disabled
   - [x] Setting -> virtualization support -> vt for Direct I/O -> **UNCHECK** Enable VT for Direct I/O
2. CFG  Unlock:
   - [x] Tool: BOOTx64.efi-For CFGLock under folder EFI->BOOT
   - [x] Rename BOOTx64.efi to a sepcific file name
   - [x] Rename BOOTx64.efi-For CFGLock to BOOTx64.efi
   - [x] Copy whole EFI folder to a FAT32 formate USB stick
   - [x] BOOT from USB
   - [x] setup_var 0xAF 0x0
3. Increase graphic card memory size
   - [x] setup_var 0x350 0x4  (128MB)
   - [x] OR setup_var 0x350 0x2  (64MB)
4. Use the original BOOTx64.efi when CFG Lock and graphic card memory size action done

## What does NOT work:

- [ ] Hibernation - When backing from Hibernation display has no output
- [ ] Airdrop
- [ ] Sidecar

## Log:

2022-08-20
- Fix shutdown restart issue
- Upgrate to adapt Monterey
- Upgrade Opencore to 0.8.3
  

2025-01-01
- Update README
- Upgrade Opencore to 1.0.3
