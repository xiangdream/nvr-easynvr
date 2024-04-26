# nvr-easynvr

1. 切换到 root 权限
  sudo su，提示输入密码，输入密码即可
2. 安装vim
 ```java
  sudo apt install vim

```

3. 添加环境变量
  ```java
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
/home/nvr-demo/hisi/nvr_target/buildStaticlibrary.sh
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
10. 
 
