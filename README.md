# nvr-easynvr

1. 切换到 root 权限
  sudo su，提示输入密码，输入密码即可
2. 安装vim
 sudo apt install vim
3. 添加环境变量
  vim  /etc/profile 修改环境变量
  添加到最后：
  export PATH="/opt/hisi-linux-nptl/arm-hisiv100-linux/target/bin:$PATH"
5. 使环境变量生效
  source /etc/profile
6. 创建目录  /home/nvr-demo/hisi
    cd  /home
    mkdir nvr-demo
   cd nvr-demo
   mkdir hisi
8. 解压nvr_target.tar.bz 到/home/nvr-demo/hisi
  tar -jxvf nvr_target.tar.bz -C /home/nvr-demo/hisi
9. nvr_target 文件名改成 nvr
  mv nvr_target nvr
10. 安装make 指令
  sudo apt-get install make
11. 
12. 编译
  /home/nvr-demo/hisi/nvr_target/buildStaticlibrary.sh
  /home/nvr-demo/hisi/nvr/source/ProductBuilder/General/General/_8channel_nvr/mkimage.sh

mkimage.sh 执行如果报错，则vim mking.sh
mksquashfs /home/root/share//ProductBuilder/romfs/   主要是文件路径不对
创建 nvrdev 目录： 
  mkdir /home/nvr-demo/hisi/nvrdev
14. 
15. 
16. 
