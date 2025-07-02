# Asscepoint-dhcp-Vlan
**สร้าง SSID**
dot11 ssid Manosh1
 vlan 10
 authentication open
 authentication key-management wpa version 2
 wpa-psk ascii password123
 mbssid gust-mode

dot11 ssid Manosh2
 vlan 20
 authentication open
 authentication key-management wpa version 2
 wpa-psk ascii password456
 
**ตั้งค่า Wireless Interface**

interface Dot11Radio0
 encryption vlan 10 mode ciphers aes-ccm
 no shutdown
 mbssid
 ssid Manosh1
 ssid Manosh2

interface Dot11Radio0
 encryption vlan 10 mode ciphers aes-ccm
 no shutdown
 mbssid
 ssid Manosh1
 ssid Manosh2

**Sub-Interface สำหรับ VLAN แต่ละตัว**

interface Dot11Radio0.10
 encapsulation dot1Q 10
 bridge-group 10

interface Dot11Radio0.20
 encapsulation dot1Q 20
 bridge-group 20

**Ethernet Trunk Interface**

interface GigabitEthernet0
 no shutdown

interface GigabitEthernet0.10
 encapsulation dot1Q 10
 bridge-group 10

interface GigabitEthernet0.20
 encapsulation dot1Q 20
 bridge-group 20

**Bridge Group และ Routing**

bridge 10 route ip
bridge 20 route ip
bridge irb

**Virtual Interface เพื่อรับ IP จาก DHCP**

interface BVI1
 ip address dhcp
