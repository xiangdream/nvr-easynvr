# nvr-easynvr

1. 切换到 root 权限
  sudo su，提示输入密码，输入密码即可
2. 安装vim
 ```java
  sudo apt install vim

```

3. 添加海思编译环境
  ```java
 tar -jxvf  /home/ipc/hisi-linux-nptl.tar.bz -C /opt
  vim  /etc/profile 修改环境变量
  添加到最后：
  export PATH="/opt/hisi-linux-nptl/arm-hisiv100-linux/target/bin:$PATH"
```
4. 使环境变量生效
  ```java
source /etc/profile
```
5. 创建目录  /home/nvr-demo/hisi
    ```java
    cd  /home
    mkdir nvr-demo
   cd nvr-demo
   mkdir hisi
    ```
6. 解压nvr_target.tar.bz 到/home/nvr-demo/hisi
  ```java
tar -jxvf nvr_target.tar.bz -C /home/nvr-demo/hisi
```
7. nvr_target 文件名改成 nvr
  ```java
mv nvr_target nvr
```
8. 安装make 指令
  ```java
sudo apt-get install make
```
9. 编译
  ```java
/home/nvr-demo/hisi/nvr/buildStaticlibrary.sh
  /home/nvr-demo/hisi/nvr/source/ProductBuilder/General/General/_8channel_nvr/mkimage.sh
```

mkimage.sh 执行如果报错，则
```java
vim mking.sh
```
```java
mksquashfs /home/root/share//ProductBuilder/romfs/   主要是文件路径不对
```
创建 nvrdev 目录： 
  ```java
mkdir /home/nvr-demo/hisi/nvrdev
```


# novartek 环境搭建
如果没有权限，新进入root
	```java
  sudo su
   ```
1.	安装依赖 参考NOVATEK_SDK_INSTALL.pptx
 ```java
sudo apt-get update
sudo apt-get -y dist-upgrade
sudo apt-get clean
sudo apt-get autoremove
sudo apt-get install build-essential libc6-dev lib32ncurses5-dev libncurses5-dev libncurses5:i386 libgl1-mesa-dev g++-multilib mingw-w64 tofrodos lib32z1 u-boot-tools zlib1g-dev bison libbison-dev flex mtd-utils vim squashfs-tools gawk cmake cmake-data liblz4-tool libmpc3 libstdc++6 device-tree-compiler android-sdk-libsparse-utils android-sdk-ext4-utils texinfo python3-pyelftools python3-crypto libssl-dev
```
2.	安装 toolchain 编辑工具
   参考 NT98331_SDK_release_v3.03.108_ns_glib_A64.tar\NT98331_SDK_release_v3.03.108_ns_glib_A64\NT98331_SDK\software\board\document 3.1章节
  	```java
  Mkdir /opt/ivot
  sudo tar –jxvf  aarch64-ca53-linux-gnueabihf-8.4.01.tar.bz2 -C /opt/ivot
   ```
3.	sdk 安装
  sdk路径 NT98331_SDK_release_v3.03.108_ns_glib_A64.tar\NT98331_SDK_release_v3.03.108_ns_glib_A64\NT98331_SDK\software\board
 	```java
  mkdir /home/dream/novatek
  tar –jxvf na51103_linux_sdk.tar.bz2
   ```
4. 变更Shell 的 symbolic link
  ls -l /bin/sh	//先查看一下連結的shell 是不是bash, 若不是就要進行切換
![image](https://github.com/xiangdream/nvr-easynvr/assets/1407942/40d8d31d-d760-4eda-a590-509558b984f0)
删除/bin/sh
```java
  rm –rf /bin/sh
  ln -s /bin/bash /bin/sh	//將symbolic link要換成/bin/bash

   ```
5.	在sdk解压的路径（na51103_linux_sdk）下面新建build.sh 编译脚本
 
```java
   cd /home/dream/na51103_linux_sdk  //进入sdk 的目录
   vim build.sh //创建build.sh 文件

   ```
build.sh 文件
```java
#!/bin/bash
echo "set environment"
source build/envsetup.sh
echo "set mode"
lunch
echo "build start"
make all
   ```
增加build.sh 为可执行
```java
   chmod 777 build.sh
   ```


