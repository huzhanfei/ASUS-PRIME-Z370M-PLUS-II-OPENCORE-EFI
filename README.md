# ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI
华硕ASUS Prime Z370M-PLUS II 黑苹果Hackintosh OpenCore EFI文件，支持核显+独显共同硬解，[OpenCore](https://github.com/acidanthera/OpenCorePkg)版本：0.6.7

## 功能

- [x] 声卡（板载）/ 网卡（板载）
- [x] 显卡（核显 + 独显）/ 硬解 4K（HEVC + H.264）
- [x] WiFi（PCI-E 设备） / 蓝牙（PEI-E 载 USB 设备）
- [x] 隔空投送 / 接力 / 随航
- [x] FaceTime / iMessage
- [x] 睿频 / HWP 变频 / 原生电源管理
- [x] 睡眠 / 键盘、鼠标唤醒
- [x] 其他白果功能（99%）

## 硬件

### 我的配置

| 硬件               | 型号                                                   |
| ------------------ | ------------------------------------------------------ |
| CPU                | Intel Core i5 9600K                                    |
| 主板               | 华硕Asus Prime Z370m-PLUS II                           |
| 显卡               | 迪兰恒进RX 580 8G战神                                  |
| 硬盘               | HP EX900 M.2 NVMe 250GB                                |
| 内存               | 英睿达8GB DDR4 3200MHz x 4                             |
| 无线 + 蓝牙        | BCM943602CS（双频1750Mbps + 蓝牙4.2）PCI-E x1 无线网卡 |
| 机箱 + 电源 + 散热 | 乔思伯V4 + 长城500W + 利民AXP-90I + 利民TF8硅脂        |
| 显示器             | AOC 2K                                                 |
| 音箱               | 漫步者R1600T III                                       |
| 键盘               | 罗技MX Keys                                        |
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
- ErP：S4+S5

### 核显配置

修改config.plist的 DeviceProperties > Add > PciRoot(0x0)/Pci(0x2,0x0) > AAPL,ig-platform-id值为下面任意一个，均可开启核显满频：

* `0300913E`：适用于有独立显卡，不使用核显驱动显示器，只用作计算。系统报告中不显示核显信息，但可使用核显加速。

* `00009B3E`：适用于没有独立显卡，使用核显驱动显示器，系统报告中显示核显信息（有独立显卡也可使用此配置，但开机速度略慢）

### HWP变频

Kexts中的`CPUFriendDataProvider.kext`为9600K专用文件，如果你使用的是其它型号的CPU，需要自行更换

### USB映射

映射端口如图所示，应该可以满足绝大多数情况，如果和你的USB端口情况不符，请自行映射替换USBPorts.kext
![](https://raw.githubusercontent.com/huzhanfei/ASUS-PRIME-Z370M-PLUS-II-OPENCORE-EFI/master/images/USBPorts.png)

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

## 更新记录
### 2021-03-15
- 升级OpenCore 0.6.7
- 升级AppleALC 1.5.8
- 升级Lilu 1.5.1
- 升级WhateverGreen 1.4.8
- 升级VirtualSMC 1.2.1
- 升级CPUFriend 1.2.3
- 升级IntelMausiEthernet 1.0.5

### 2020-11-17
- 升级OpenCore 0.6.3
- 升级AppleALC 1.5.4
- 升级Lilu 1.4.9
- 升级WhateverGreen 1.4.4
- 升级VirtualSMC 1.1.8
- 升级CPUFriend 1.2.2
- 升级IntelMausiEthernet 1.0.4

### 2020-09-22
- 升级OpenCore 0.6.1
- 升级AppleALC 1.5.2
- 升级Lilu 1.4.7
- 升级WhateverGreen 1.4.2
- 升级VirtualSMC 1.1.6

### 2020-08-11
- 升级AppleALC 1.5.1
- 升级Lilu 1.4.6
- 升级WhateverGreen 1.4.1
- 升级CPUFriend 1.2.1
- 升级VirtualSMC 1.1.5