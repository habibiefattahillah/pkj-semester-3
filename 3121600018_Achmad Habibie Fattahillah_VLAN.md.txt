# VLAN

## Topologi
[![Topologi.png](https://i.postimg.cc/Jn4Wj82G/Topologi.png)](https://postimg.cc/QBPPr2s3)
<br>

### Register VLAN pada setiap Router dan Switch
[![VLANDatabase.png](https://i.postimg.cc/qM90S9z5/VLANDatabase.png)](https://postimg.cc/rKCvtZG1)
<br>

### Router 0
#### Enkapsulasi dan beri IP pada setiap VLAN
[![Config-IPVLAN.png](https://i.postimg.cc/J7YRcymm/Config-IPVLAN.png)](https://postimg.cc/py8NPLp1)
<br>

### Switch
#### Konfigurasi VLAN pada Switch
|  Devices 	|    Interfaces    	|  Mode  	|     VLAN     	|
|:--------:	|:----------------:	|:------:	|:------------:	|
| Switch 0 	| Fa0/1 (Switch 1) 	|  Trunk 	|  Select All  	|
|          	|    Fa0/2 (PC0)   	| Access 	|  10 (admin)  	|
|          	|    Fa0/3 (PC1)   	| Access 	|   20 (dev)   	|
| Switch 1 	| Fa0/1 (Router 0) 	|  Trunk 	|  Select All  	|
|          	| Fa0/2 (Switch 0) 	|  Trunk 	|  Select All  	|
|          	| Fa0/3 (Switch 2) 	|  Trunk 	|  Select All  	|
|          	|    Fa0/4 (PC2)   	| Access 	|  10 (admin)  	|
|          	|    Fa0/5 (PC3)   	| Access 	|   20 (dev)   	|
|          	|    Fa0/6 (PC4)   	| Access 	| 30 (manager) 	|
| Switch 2 	| Fa0/1 (Switch 1) 	|  Trunk 	|  Select All  	|
|          	|    Fa0/2 (PC5)   	| Access 	|  10 (admin)  	|
|          	|    Fa0/3 (PC6)   	| Access 	|   20 (dev)   	|
|          	|    Fa0/4 (PC7)   	| Access 	| 30 (manager) 	|
<br>
Mode Trunk pada setiap port antara Switch ke Switch atau ke Router.
<br> Mode Access pada setiap port antara Switch ke PC-Client.

### PC

| Devices 	|     IPv4     	| Default Gateway 	|
|:-------:	|:------------:	|:---------------:	|
|   PC0   	| 192.168.10.6 	|   192.168.10.1  	|
|   PC1   	| 192.168.20.6 	|   192.168.20.1  	|
|   PC2   	| 192.168.10.5 	|   192.168.10.1  	|
|   PC3   	| 192.168.20.5 	|   192.168.20.1  	|
|   PC4   	| 192.168.30.3 	|   192.168.30.1  	|
|   PC5   	| 192.168.10.4 	|   192.168.10.1  	|
|   PC6   	| 192.168.20.4 	|   192.168.20.1  	|
|   PC7   	| 192.168.30.2 	|   192.168.30.1  	|

### Test Ping To Other VLAN


[![TestPing.png](https://i.postimg.cc/R0mmVK11/TestPing.png)](https://postimg.cc/hX262J5h)
