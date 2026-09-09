# Lab1：日志实验环境验收
## 一、实验目的
验证VMware、Ubuntu虚拟机、网络、虚拟硬件、rsyslog日志组件是否部署正常，完成实验环境验收。

## 二、实验环境
宿主机：Windows
虚拟化软件：VMware Workstation Pro
虚拟机系统：Ubuntu
虚拟机配置：2核CPU，5.7G内存，40G磁盘

## 三、实验步骤与结果
### 任务一：检查VMware版本
打开VMware，点击Help → About VMware Workstation，查看版本信息，截图保存。

### 任务二：虚拟机硬件信息检查
1. 查看CPU信息
命令：`lscpu`
结果：架构x86_64，2核，VMware虚拟化支持正常。

2. 查看内存信息
命令：`free -h`
结果：总内存5.7Gi，交换分区4.0Gi，内存可用充足。

3. 查看磁盘信息
命令：`lsblk`
结果：磁盘sda总大小40G，分区挂载正常。

### 任务三：网络检查
命令：`ip a`
结果：网卡ens33状态UP，获取IP：192.168.249.130，网络连通正常。

### 任务四：日志组件检查
1. 查看rsyslog服务状态
命令：`systemctl status rsyslog`
结果：rsyslog.service处于active(running)，开机自启，日志服务正常运行。

2. 查看系统日志
命令：`tail -n 20 /var/log/syslog`
结果：成功读取系统最近日志，日志持续生成。

3. 查看认证日志
命令：`tail -n 20 /var/log/auth.log`
结果：成功读取用户登录相关认证日志。

## 四、实验结论
本次实验完成全部环境验收项目，VMware、Ubuntu虚拟机硬件、网络、rsyslog日志组件均正常工作，满足后续日志分析实验要求。