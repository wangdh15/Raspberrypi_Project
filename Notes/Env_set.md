## 树莓派学习之环境配置
## 王道烩 2018.9.28

### 安装操作系统

首先要有一个SD卡，最好32G，然后需要一个读卡器，然后有一台电脑。电脑可以使用etcher来进行制作，各种平台都有。

然后将sd卡插入开机就能够进行安装。

[etcher下载地址](https://etcher.io/)

### 更新软件源

为了加快速度，可以使用国内的raspi的软件源。可以使用清华大学的软件源。
具体使用方法见说明。

[raspi清华大学软件源](https://mirrors.tuna.tsinghua.edu.cn/help/raspbian/)

修改完之后可以`sudo apt-get upgrade`进行操作系统更新。

### 摄像头

`raspistill`通过不同额配置参数可以进行拍照以及录像。

### 显示器全屏

在终端输入`raspi-config`，然后选择`overscan`，然后将其关闭。如果需要修改分辨率的话，可以选择`Resolution`，然后将其设置为`Default`。

### 硬盘分区

`sudo fdisk -l` 查看自己的设备是否被识别到。

`sudo fdisk /dev/sda` 然后按照提示进行操作。

- 输入P查看现有分区
- 输入d删除分区
- 输入n划分新分区

然后按照提示操作下去。

然后格式化磁盘

`sudo mkfs.ext4 /dev/sda1`

然后使用`mount`命令将其挂载到一个文件夹上

`sudo mount /dev/sda1 ~/File`


如果想要以后开机自动挂载，那么需要修改`/etc/fstab`

然后按照其中的格式添加一行即可。

### Transmission

`sudo apt-get install transmission`即可。

可以下载一个transmission，挂个硬盘，就可以一直做种。

如果将种子和文件同时移动到另一个地方，可以在transmission中选择打开种子，然后选择不下载，并将set文件位置。如果文件之间移动之后，可以右键种子，set location，然后选择文件位置即可。
