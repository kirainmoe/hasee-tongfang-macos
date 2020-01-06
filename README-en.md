<p align="center">

<img src="https://i.loli.net/2020/01/06/6ZNseqdxyGVlwPb.png" width="300px" alt="logo">

</p>

<h1 align="center">macOS on Tongfang Laptops</h1>

<p align="center">
<img src="https://img.shields.io/badge/build-passing-brightgreen.svg"/> 
<a href="https://aya-buildbot.kirainmoe.com">
    <img src="https://img.shields.io/badge/download-release-blue.svg"/> 
</a>
<img src="https://img.shields.io/badge/coverage-98%25-brightgreen.svg"/> <img src="https://img.shields.io/badge/macOS_version-10.15.2-9cf.svg"/> <img src="https://img.shields.io/badge/built_by-Yume_Maruyama-ff69b4.svg"/> 
</p>

![QQ20200106-200142@2x.jpg](https://i.loli.net/2020/01/06/jHEMaG3wPbiKWc2.jpg)

<h3 align="center">
    <a href="https://efi.kirainmoe.com/">Download EFI</a> /
    <a href="https://github.com/kirainmoe/hasee-tongfang-macos/blob/master/Changelog.md">Changelog</a> / <a href="https://github.com/kirainmoe/hasee-tongfang-macos/blob/master/README.md">简体中文</a>
</h3>

This repo contains the Clover config for installing latest macOS on Tongfang (Tsinghua Tongfang) barebones-based 8th/9th generation platform laptops, like some Hasee, Mechrevo, OverPowered, Monster, Avell devices.

## Tutorial

- Choose the branch on the basis of your device specification and download the correct config zip
- Download a latest version of macOS from somewhere
- Use BalenaEtcher / Unibeast / etc. to make a installer flash
- Part your disk that you are going to install macOS (You should have a GUID partition table and a 200M+ ESP part)
- Replace the original clover config with the config from this repo
- Disable `Secure Boot`, `Launch CSM` and change to `UEFI Mode` in BIOS
- Boot from flash and install macOS
- Enjoy!

## Better Experience

[Optimize Script](https://hackintosh.kirainmoe.com/an-zhuang-hou/an-zhuang-hou-de-chang-jian-wen-ti-jie-da#postinstall-you-hua-jiao-ben-shi-shen-me-wei-shen-me-xu-yao-zhi-hang-ta)：Optimize sleep function, enable HIDPI...

[Useful Scripts](https://hackintosh.kirainmoe.com/an-zhuang-hou/chang-yong-ming-ling-he-you-hua)

[Project: STAR BEAT! - macOS keyboard light controller](https://github.com/kirainmoe/project-starbeat/releases) (Support ITE revision 0.02 only)

[AUCC - keyboard light controller](https://github.com/rodgomesc/avell-unofficial-control-center) (Support ITE revision 0.03 only)


## Compatibility

### macOS version

**Tips: We no longer support macOS 10.13 (High Sierra) and macOS 10.14(Mojave) since 2020.1.3.**

| macOS version | Build version | Compatible | Tested by Author | Tested by Users |
|-------|---------|--------|------------|----------|
| 10.14.6 | 18G87 | ✅ yes  | ✅ yes  | ✅ yes  |
| 10.15   | 19A583 | ✅ yes  | ✅ yes  | ✅ yes  |
| 10.15.1 | 19B88 | ✅ yes  | ✅ yes  | ✅ yes  |
| 10.15.2 | 19C57 | ✅ yes  | ✅ yes  | ✅ yes  |

### Models

> Notes: I was not sure that some models can work perfectly with this config. The models listed in the following table are those would be theoretically supported gussing by their barebone model.

#### Tips

- If you have 8th gen platform laptops, try one of { *master, kp7ec, kp7gc* }.
-  If you have 9th gen platform laptops, try one of { *ct7gk, ct7gs* }.

| Barebone | Models Theoretically Supported | Branch |
|-----|------|-----|
| GK5CN5X <br> GK5CN6X <br> GK5CN6Z <br> GK5CN5Z | Hasee Z7(m)-KP7/5(G)Z <br> Shinelon Yao 7000 II <br> Mechrevo Z2 Air <br>XMG Neo 15<br>OverPowered Gaming Laptop 15<br>MACHENIKE F117-B1/2 | [master](https://github.com/kirainmoe/hasee-tongfang-macos) | 
| GI5CN54 <br> GJ5CN64 | Hasee Z7(m)-KP7/5EC | [kp7ec](https://github.com/kirainmoe/hasee-tongfang-macos/tree/kp7ec) |
| GI5CN54 <br> GJ5CN64 | Hasee Z7(m)-KP7/5GC/A<br>Avell A52-5 BS<br>CyberPower NB-408-109<br>Machenike T90 | [kp7gc](https://github.com/kirainmoe/hasee-tongfang-macos/tree/kp7gc) |
| GK7CP6R | Hasee Z7-CT7GK / Z7m-CT7GS / Z7-CT7VH / G7-CT7VK<br>Illegear Rogue Laptop<br>XMG Core 17<br>Mechrevo X3<br>CyberPowerPC Tracer-III-17<br>Monster Tulpar T7 v19.3  | [ct7gk](https://github.com/kirainmoe/hasee-tongfang-macos/tree/ct7gk) <br> [ct7gs](https://github.com/kirainmoe/hasee-tongfang-macos/tree/ct7gs) |
| GK7CN6S<br>GK7CN5S | Monster Abra A7 v10.1 <br>Overpowered 17+ laptop  | [master](https://github.com/kirainmoe/hasee-tongfang-macos) |

## Device Specifications

| Component | Model | Comment |
|--|--|---|
| CPU | Intel Core(TM) i7-8750H (9750H)  | i5-8300H and i5-9300H are compatible |
| GPU | Intel UHD630 / Nvidia GTX 1050(Ti),1060, 1650, 1660Ti; RTX2060 | Nvidia GPU has no solution currently (and permanently). For more reason, please refer to [this.](https://github.com/kirainmoe/hasee-tongfang-macos/wiki/%E5%AE%89%E8%A3%85%E5%90%8E%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94#%E9%82%A3%E4%B8%BA%E4%BB%80%E4%B9%88%E7%8B%AC%E6%98%BE%E6%97%A0%E6%B3%95%E9%A9%B1%E5%8A%A8) |
| RAM | Micron Crucial 8GB+8GB | |
| NVMe | WD Black SN750 NVME SSD 500G | Samsung PM981/970EvoPlus were not supported by macOS | 
| SATA SSD | Phison SATA SSD 128G | | 
| Wireless | BCM94360CS2 | Intel wireless cards have no driver. |
| Ethernet | Realtek RTL8168H | |
| Audio | Realtek ALC269vc | |

### What's working

- Turbo boost and CPU frequency stage.
- Intel UHD630
- Brightness control and Fn keys (Fn keys controlling is not available for Tongfang GK7CP6R devices)
- I2C HID Touchpad
- Realtek Ethernet
- Bluetooth (No Airdop if you are using Intel Bluetooth)
- Audio (Realtek ALC268vc, using AppleALC + layout-id 29/88)
- Battery status (using Clover hotpatch)
- USB 3.0 and Type-C
- Sleep
- Camera
- etc.

### What's partially working

- PS/2 Touchpad (Tongfang GI5CN54/GJ5CN64)

### What's not working

- Nvidia discrete GPU (used SSDT to disable it)
- Intel Wireless Card
- HDMI/mini DP (which is connected to DGPU directly)
- Card reader

## Contribute

Issues & Pull request are welcomed.

## License

`hasee-tongfang-macos` is [MARUYAMA](https://github.com/kirainmoe/hasee-tongfang-macos/blob/master/LICENSE) Licensed. You can use the config for free under the Maruyama License.