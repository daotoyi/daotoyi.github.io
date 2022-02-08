# SSD性能提升


# #above can't work in loveit theme.
# #+toc: true
# #+comment: true

* 固态硬盘接口

性能从低到高排序为:
- SATA 接口
  - SATA Revision 1.0
  - SATA Revision 2.0
  - SATA Revision 3.0
    
- M.2 接口
  - 一种支持 SATA 协议
  - 一种支持 NVME 协议
    协议性能更好，走 PCIE 通道，带宽高达 32G
    
- PCI-E 接口
  - 直接通过 PCI-E 总线和 CPU 直连，节省通过内存的流程,性能是最强的，理论最高速度达到 32Gbps。

* AHCI 协议 
高级串行 ATA 功能接口标准.

使用机械硬盘时，主板 AHCI 是不打开的。使用速度较高的固态硬盘时，就必须要开启 AHCI 了， **通过 NCQ 功能，提升电脑整体速度** 。

* 设置固态硬盘

- 如果使用的是 SATA 接口，要区分 SATA2.0 接口和 SATA3.0 接口；
- 如果使用的是 PCI-E 接口，则要确认插槽为全速插槽;
- 进入主板 BIOS 设置，开启第二点所说的 AHCI 协议，关闭硬盘节能。
- 设置固态硬盘的 4K 对齐.

