# 更新日志 Changelog

## 2020.3.10

- 更新 OpenCore 为官方 0.5.6 版本，并同步更新 `config.plist` (Update OpenCore to 0.5.6)
- 重新修改并编译 NdkBootPicker.efi (Add modifed `NdkBootPicker.efi`)
- VoodooI2C.kext 替换为 @Goshin 修改的新版本，使用普通点按代替压力点按。 (Replace `VoodooI2C.kext`)

## 2020.3.11

- <s>删除可能不需要的显卡 Framebuffer 参数。(Delete some unused IGPU framebuffer properties)</s>

## 2020.3.12

- 更新 Lilu, WhateverGreen 为官方最新版以完善对 4K 屏幕的支持。 (Update Lilu & WhateverGreen kext)
- 定制 OpenCore GUI 主题。 (Modify OC GUI theme)

## 2020.3.13

- 还原 `framebuffer-stolenmem` 和 `framebuffer-fbmem`，若去掉此两参数会使 GJ5CN64 / GI5CN54 模具发生内核崩溃；驱动 4K 屏幕需要删除这两个参数，将交由 Tongfang Hackintosh Utility 处理。
- Restore `framebuffer-stolenmem` and `framebuffer-fbmem`, for deleting those properties will cause a kernel panic on GJ5CN64 / GI5CN54 laptops.

## 2020.3.18

- 从 [Goshin/VoodooI2C:impv-mt](https://github.com/Goshin/VoodooI2C/tree/impv-mt) 重新编译 `VoodooI2C`，改善 I2C 触摸板的多指手势支持。
- Recompile VoodooI2C from [Goshin/VoodooI2C:impv-mt](https://github.com/Goshin/VoodooI2C/tree/impv-mt) to improve multi-touch gesture support.

## 2020.3.22

- <s>还原 GC 系列机型的 USB 定制拓展为 USBPorts.kext</s>

## 2020.3.23

- USB: 取消 3.22 的更改
- config: `NVRAM/WriteFlash = True`

## 2020.3.26

- 更新 WhateverGreen.kext 为 1.3.8
- 添加 `igfxfw=2` 引导参数，以解决部分九代机型睡眠唤醒后核显频率问题。有关具体缘由，移步 https://github.com/acidanthera/bugtracker/issues/748
- 更新 `SSDT-DDGPU.aml`，并添加 `_PTS => XPTS` 重命名，可能解决部分九代机型睡眠死机问题
- 去除 `HECI -> IMEI` (这次真的交给 WhateverGreen 处理了)

## 2020.4.6

- 众口难调，GJ5CN64 / GI5CN54 不再默认使用 ApplePS2SmartTouchpad.kext，日后将一直采用 Rehabman 的 VoodooPS2Controller.kext
- 尝试修复 GI5CN54 模具的 USB 定制问题（未测试，需要观察）
- 更新 BrcmPatchRAM3 驱动

## 2020.4.7

- 更新 OpenCore 到官方 0.5.7 版本，同步更新 OpenRuntime.efi 和 OpenUsbKbDxe.efi
- 更新 NdkBootPicker 为自编译修改版以适配 0.5.7
- 新的 OC 引导主题
- config.plist 适配 0.5.7 格式

## 2020.4.8

- 修复 Windows 蓝屏 0xc000000d 问题 (`RebuildAppleMemoryMap->True, SyncRuntimePermissions->True`)
- 更新 VoodooI2CHID.kext，现在可以在 Recovery 模式下使用触摸板，并且不再需要加载 IOGraphicsFamily.kext
- 添加 NVMeFix.kext，优化第三方 NVMe 硬盘的电源管理；同时可能会修复三星 PM981 的问题
- 添加 HibernationFixup.kext，若无法正常睡眠请尝试勾选此项