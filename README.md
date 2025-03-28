# IOTassess
# 局域网主机扫描报告

**扫描时间：** 2025年3月27日  
**扫描命令：** `nmap -A -O -sV -oN ./AO.txt 192.168.88.1/24`  
**共扫描主机数：** 256  
**存活主机数：** 14(1 for my host, 1 for my kali, 12 devices in IoT system)

---

## 主机列表与服务概况

###  192.168.88.1
- **设备厂商：** MikroTik Router
- **MAC 地址：** DC:2C:6E:6C:08:48
- **操作系统：** Linux 2.6.32 - 3.13 / RouterOS 6.49.17
- **开放端口：**
  - 21/tcp - FTP (MikroTik router ftpd 6.49.17)
  - 22/tcp - SSH (RouterOS sshd)
  - 23/tcp - Telnet
  - 53/tcp - DNS (响应异常)
  - 80/tcp - HTTP（Router 配置页面）
  - 2000/tcp - Bandwidth-Test Server
  - 8291/tcp - 未识别服务

---

###  192.168.88.20
- **设备厂商：** Raspberry Pi
- **MAC 地址：** D8:3A:DD:94:80:67
- **操作系统：** Debian / Linux 5.x
- **开放端口：**
  - 22/tcp - SSH (OpenSSH 8.4p1)
  - 139, 445/tcp - Samba 服务
  - 8081/tcp - HTTP (Motion 摄像头界面)

---

###  192.168.88.50
- **厂商：** Siemens Industrial
- **MAC 地址：** 8C:F3:19:C3:0C:B5
- **操作系统：** Linux 4.x / RouterOS 7.x
- **开放端口：**
  - 22/tcp - SSH (OpenSSH 9.2p1)

---

###  192.168.88.150
- **厂商：** Intel Corporate
- **MAC 地址：** 10:F6:0A:FA:2B:89
- **操作系统：** 无法识别
- **开放端口：**
  - 22, 5000/tcp - tcpwrapped

---

###  192.168.88.175
- **厂商：** TP-Link
- **MAC 地址：** 54:AF:97:BB:F6:13
- **开放端口：**
  - 9999/tcp - abyss?

---

###  192.168.88.178
- **厂商：** Intel
- **MAC 地址：** 64:49:7D:86:6E:06
- **开放端口：** 无响应（全部 filtered）

---

###  192.168.88.183
- **主机名：** STU013-IT092087
- **MAC 地址：** 10:F6:0A:FA:2B:89
- **操作系统：** Windows
- **开放端口：**
  - 多个端口被 tcpwrapped：135, 139, 445, 808, 1311, 1801, 2103, 2105, 2107, 2179, 4002, 27000

---

###  192.168.88.186
- **设备信息：** Samsung mobile phone
- **MAC 地址：** 66:D7:59:5B:C2:61
- **开放端口：** 全部 closed

---

###  192.168.88.189
- **厂商：** Siemens Industrial
- **MAC 地址：** 8C:F3:19:C3:0C:B5
- **开放端口：**
  - 22/tcp - SSH (OpenSSH 9.2p1)
- **备注：** SSH 密钥与 192.168.88.50 完全一致

---

###  192.168.88.205
- **厂商：** Samjin
- **MAC 地址：** 28:6D:97:91:D6:D8
- **开放端口：**
  - 443/tcp - lighttpd 1.4.53（返回 503）

---

###  192.168.88.206
- **厂商：** Philips Hue
- **MAC 地址：** EC:B5:FA:8C:0C:91
- **设备类型：** Hue Bridge 2.0
- **开放端口：**
  - 80, 443/tcp - HTTP/HTTPS (nginx)
  - 8080/tcp - OpenPegasus WBEM

---

###  192.168.88.207
- **厂商：** Amazon
- **MAC 地址：** 10:09:F9:04:B8:0E
- **开放端口：**
  - 1080/tcp - socks5
  - 8888/tcp - tcpwrapped

---

## 附加信息

- ⚠️ 多个主机使用重复 SSH 密钥，可能是镜像部署。
- ⚠️ 多主机存在 tcpwrapped 端口，需进一步鉴别。
- 建议对未识别服务使用 UDP 扫描（`-sU`）进一步分析。

---
