# ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI
华硕ASUS Prime Z370M-PLUS II 黑苹果Hackintosh OpenCore EFI文件，支持核显+独显共同硬解，[OpenCore](https://github.com/acidanthera/OpenCorePkg)版本：0.5.9

## 功能

- [x] 声卡（板载）/ 网卡（板载）
- [x] 显卡（核显 + 独显）/ 硬解 4K（HEVC + H.264）
- [x] WiFi（PCI-E 设备） / 蓝牙（PEI-E 载 USB 设备）
- [x] 隔空投送 / 接力 / 随航
- [x] FaceTime / iMessage
- [x] 睿频 / HWP 变频 / 原生电源管理
- [x] 睡眠 / 键盘、鼠标唤醒（未完整测试）
- [x] 其他白果功能（99%）

## 硬件

### 我的配置

| 硬件               | 型号                                                   |
| ------------------ | ------------------------------------------------------ |
| CPU                | Intel Core i5 9600K                                    |
| 主板               | 华硕Asus Prime Z370m-PLUS II                           |
| 显卡               | 迪兰恒进RX 580 8G战神                                  |
| 硬盘               | HP EX900 M.2 NVMe 250GB                                |
| 内存               | 英睿达8GB DDR4 2400MHz x 2                             |
| 无线 + 蓝牙        | BCM943602CS（双频1750Mbps + 蓝牙4.2）PCI-E x1 无线网卡 |
| 机箱 + 电源 + 散热 | 乔思伯V4 + 长城500W + 利民AXP-90I + 利民TF8硅脂        |
| 显示器             | AOC 2K                                                 |
| 音箱               | 漫步者R1600T III                                       |
| 键盘               | 酷冷至尊 烈焰枪                                        |
| 鼠标               | 罗技MX Master 2S                                       |




## 使用
### BIOS设置
#### 关闭
- 快速启动
- 安全启动
- VT-d（如果`DisableIoMapper`设置为True，则可以开启）
- CSM
- Intel SGX
- Intel Platform Trust
- CFG Lock

#### 开启
- VT-x
- 大于4G解码（Above 4G decoding）
- EHCI/XHCI Hand-off
- 操作系统类型：Windows 8.1/10 UEFI Mode
- DVMT Pre-Allocated(iGPU Memory): 64MB
- SATA Mode: AHCI

### HWM变频

Kexts中的`CPUFriendDataProvider.kext`为9600K专用文件，如果你使用的是其它型号的CPU，需要自行更换

### USB映射

该主板我用起来暂时还没有发现USB问题，唤醒功能正常，因此没有做USB端口映射，如果有需要的话请自行映射


### 修改SMBIOS
自行生成SMBIOS替换图中所示内容：
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/SMBIOS.png)


## 截图
### 关于本机
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/About.png)
### 显卡信息
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/DisplayInfo.png)
### 变频
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/IntelPowerGadget.png)
### 硬解
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/VideoProc.png)
### iMessage
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/iMessage.png)
### 隔空投送
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/AirDrop.png)