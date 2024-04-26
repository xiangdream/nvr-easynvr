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
  tar -jxvf nvr_source_code.tar.bz -C /home/nvr-demo/hisi
9. 
10. 
11. 
