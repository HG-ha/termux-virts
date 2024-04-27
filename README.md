### 关于此项目
1. 在Termux中一键部署、管理qemu虚拟机，支持添加、删除、启停、快照管理、支持自定义参数启动虚拟机
2. 由于支持快照，建议安装虚拟机后首先制作初始环境的快照，以便随时恢复到初始环境
3. 虚拟机镜像由个人制作上传，后续将支持更多发行版、软件版本
4. 其他Linux请先自行安装qemu、jq、wget命令，或等待后续适配
5. 如需查看命令帮助，使用：vbn help

### 正确使用操作
1. 安装vbn
2. 安装需要的虚拟机
3. 为虚拟机创建初始快照，方便随时恢复到初始环境
4. 开始使用虚拟机

### 安装vbn
#### 1. Termux
```
pkg install wget -y && wget --no-check-certificate -O $PREFIX/bin/vbn "https://hub.gitmirror.com/https://raw.githubusercontent.com/HG-ha/Termux_virts/main/vbn" 
chmod +x $PREFIX/bin/vbn
```
#### 2. 其他Linux
```
# 按照对应平台方法安装qemu，jq，wget命令后再使用
wget --no-check-certificate -O /usr/bin/vbn "https://hub.gitmirror.com/https://raw.githubusercontent.com/HG-ha/Termux_virts/main/vbn"
chmod +x /usr/bin/vbn
```

### 当前支持的虚拟机列表
1. centos7-x86_64-2009.qcow2
   ```
    使用镜像：CentOS-7-x86_64-Everything-2009.iso
    软件包：最小化安装
    系统设计容量：40G
    实际大小：1.7G
    语言：简体中文（中国）
    用户名：root
    密码：123456
    环境配置：初始化环境，无任何操作
    备注：建议使用vnc进行连接，不要直接输出界面到当前termux终端，否则可能启动失败
   ```
2. alpine-3.19.1-x86_64.qcow2
   ```
    使用镜像：alpine-virt-3.19.1-x86_64.iso
    软件包：
    系统设计容量：40G
    实际大小：378M
    语言：
    用户名：root
    密码：123456
    环境配置：已配置官方源，网卡dhcp模式
    备注：
   ```
3. alpine-3.18.0-x86_64.qcow2
   ```
    使用镜像：alpine-virt-3.18.0-x86_64.iso
    软件包：
    系统设计容量：20G
    实际大小：92M
    语言：
    用户名：root
    密码：alpine
    环境配置：已配置官方源，网卡dhcp模式
    备注：
   ```
4. bt_centos7-x86_64-2009.qcow2
   ```
    使用镜像：CentOS-7-x86_64-Everything-2009.iso
    软件包：最小化安装
    系统设计容量：40G
    实际大小：2.7G
    语言：简体中文（中国）
    用户名：root
    密码：123456
    虚拟机外部面板地址: http://127.0.0.1:25479/ed978faa
    username: yiming
    password: yiming
    环境配置：安装了宝塔面板8.0.6
    备注：建议使用vnc进行连接，不要直接输出界面到当前termux终端，否则可能启动失败。开机后使用bt 3命令运行宝塔
   ```
5. bt_alpine-3.18.0-x86_64.qcow2
   ```
    使用镜像：alpine-virt-3.18.0-x86_64.iso
    软件包：
    系统设计容量：40G
    实际大小：1.3G
    语言：
    用户名：root
    密码：alpine
    内网宝塔面板地址: http://127.0.0.1:11306/eaeab87a
    宝塔username: oqlsnrhi
    宝塔password: 71e1f417
    环境配置：安装了宝塔面板8.0.6
    备注：开机后使用bt 3命令运行宝塔，若要在该版本上安装docker，使用命令：apk add docker docker-compose
   ```
6. docker_alpine-3.18.0-x86_64.qcow2
   ```
    使用镜像：alpine-virt-3.18.0-x86_64.iso
    软件包：默认, docker
    系统设计容量：20G
    实际大小：368M
    语言：
    用户名：root
    密码：alpine
    环境配置：已配置官方源，网卡dhcp模式，安装了docker
    备注：
   ```
7. qwenapi_alpine-3.18.0-x86_64.qcow2
   ```
    使用镜像：alpine-virt-3.18.0-x86_64.iso
    软件包：默认, docker
    系统设计容量：20G
    实际大小：464M
    语言：
    用户名：root
    密码：alpine
    环境配置：已配置官方源，网卡dhcp模式，安装了通义千问API，API文档：https://github.com/LLM-Red-Team/qwen-free-api
    备注：
   ```
8. kali（官方Termux支持）
   ```
    使用镜像：kali nethunter-rootless 2024.1
    软件包：
    系统设计容量：
    实际大小：11G（下载3.1G）
    语言：
    用户名：
    密码：
    环境配置：
    备注：官方Linux，2024.1版本, 为proot环境, 无法访问init（安卓限制）
   ```