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
    - 192.168.1.90
  - Run nmap against 192.168.1.1/24 
    - ```nmap 192.168.1.1/24```
    - Did not give enough information to determine what machine is which
    - ```nmap -sV 192.168.1.1/24```
      - 192.168.1.100 
        - Elastic Search | Ubuntu
      - 192.168.1.105
        - Apache | Ubuntu
  - Open http://192.168.1.105
    - Try to find "secret" page
      - ```dirb http://192.168.1.105```
        - Returned
          - http://192.168.1.105/server-status
            - Access Forbidden
          - http://192.168.1.105/webdav
            - Username:Password Protected
      - ```dirb http://192.168.1.105/company_folders```
        - Returned 0
      - Scrolled through pages
        - Error file missing please refer to company_folders/secret_folder
         ![](/img/web4.png)
