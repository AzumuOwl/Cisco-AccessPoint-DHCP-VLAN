# 📡 Access Point Configuration with Multi-SSID, VLAN, and DHCP

โปรเจกต์นี้เป็นการตั้งค่า **Cisco Autonomous Access Point** เพื่อใช้งาน **หลาย SSID** โดยแต่ละ SSID แยก VLAN กัน และสามารถรับ IP ผ่าน DHCP จาก Router ได้

---

## ✅ สร้าง SSID

```shell
dot11 ssid Manosh1
 vlan 10
 authentication open
 authentication key-management wpa version 2
 wpa-psk ascii password123
 mbssid guest-mode

dot11 ssid Manosh2
 vlan 20
 authentication open
 authentication key-management wpa version 2
 wpa-psk ascii password456
 mbssid guest-mode

```shell
---

## ✅ สร้าง SSID
