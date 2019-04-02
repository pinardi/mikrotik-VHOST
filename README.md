# mikrotik-VHOST
make mikrotik at virtualbox
make identity mikrotik
```bash
/system identity set name=jweb.com
```
change password
```bash
/password
```
setting interface
```bash
/interface set ether1 name=internet
/interface set ether2 name=lan
```
add ip address
```bash
/ip address add address=192.168.12.121/24 interface=internet
/ip address add address=10.11.12.10/24 interface=lan
```
setup dhcp
```bach
/ip dhcp-server setup
```
add dns server and static
```bash
/ip dns set server=192.168.1.2,192.168.1.3 allow-remote-request=yes cache-size=6144
/ip dns static add name=nslan address=10.11.12.10
```
add firewall
```bash
/add firewall nat add chain=srcnat out-interface=internet action=masquerade
```
add gateway
```bash
/ip route add gateway=192.168.12.254
```
