# 常用Bash命令

网络

```sh
//查看网卡信息
ifconfig
ip addr 
//启动关闭网卡
sudo ip link set eth0 up
sudo ip link set eth0 down
//设置mtu值
sudo ip link set eth0 mtu 8000
//编辑netplan
sudo nano /etc/netplan/fenix-default.yaml

####################################
network:
  version: 2
  renderer: NetworkManager
  ethernets:
    eth0:
      dhcp4: no
      addresses:
        - 192.168.3.16/24
      gateway4: 192.168.3.1
      nameservers:
          addresses: [8.8.8.8, 8.8.8.4]
####################################


```

服务

```sh
//新建服务
cd  /etc/systemd/system
sudo nano myapp.service
//编辑服务内容
####################################
[Unit]
Description=Your Description
After=network.service

[Service]
Type=simple
User=rpdzkj
Group=rpdzkj
WorkingDirectory=/home/rpdzkj/run
ExecStart=python3 /home/rpdzkj/run/main.py
PrivateTmp=true
Restart=on-failure

[Install]
WantedBy=multi-user.target
####################################

// 开启服务
sudo systemctl start myapp.service
// 重启服务
sudo systemctl restart myapp.service
// 停止服务
sudo systemctl stop myapp.service
//查看log
sudo journalctl -u myapp.service
// 重载
sudo systemctl daemon-reload
```

装pip包

```sh
echo "y" | apt-get install update

echo "y" | apt-get install pip

pip config set global.index-url https://mirrors.bfsu.edu.cn/pypi/web/simple

pip install opencv-python
```

装载大恒相机驱动

```
tar -zxvf </tar.gz/>
cd 
```
ARM linux 安装node。js

```
sudo apt-get update && sudo apt-get install -y ca-certificates curl gnupg
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
NODE_MAJOR=20
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
sudo apt-get update && sudo apt-get install nodejs -y
```
atom协议安装
```
安装Node.js
下载&配置Atomicals-JS-Master
npm install -g typescript
npm run build
npm install -g yarn
yarn install
yarn cli wallet-init
#这一步生成钱包
```





