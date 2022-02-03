# Project 2
## RedTeam vs. BlueTeam


### Devices
- Kali
- Capstone
- Elk 

### Set Up Beats 
Need to set up beats in order to log the attacks. 

Steps to set up:
 - Log into Capstone
   - ```vagrant:tnargav```
 - ```sudo su```
 - ```filebeat modules enable apache```
 - ```filebeat setup```
 - ```metricbeat modules enable apache```
 - ```metricbeat setup```
 - ```packetbeat setup```
 - ```systemctl restart filebeat```
 - ```systemdtl restart metricbeat```
 - ```systemctl restart packetbeat```
  

### Attacking Capstone
- Determine capstone ip
  - First find kali ip
    - ```ifconfig```
    - ```192.168.1.90```
    - 
