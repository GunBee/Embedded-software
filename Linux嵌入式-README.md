# Embedded-software
Embedded software learning

1、设备树编译
设备树源文件扩展名为.dts，将.dts 编译为.dtb，需要用到 DTC 工具，DTC 工具源码在 Linux 内核的 scripts/dtc 目录下，
DTC 工具依赖于 dtc.c、flattree.c、fstree.c 等文件，最终编译并链接出 DTC 这个主机文件，
如果要编译 DTS 文件的话只需要进入到 Linux 源码根目录下，
然后执行如下命令：(对于 RK3568，需要指定 ARCH=arm64)
make ARCH=arm64 all
或者：
make ARCH=arm64 dtbs

注意:
“make ARCH=arm64 all”命令是编译 Linux 源码中的所有东西，包括
uImage/zImage，.ko 驱动模块以及设备树，如果只是编译设备树的话建议使用“make 
ARCH=arm64 dtbs”命令

2、设备树语法
设备树是采用树形结构来描述板子上的设备信息的文件，每个设备都是一个节点，叫做设
备节点，
