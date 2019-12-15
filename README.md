## dangerrulez   
  http://danger.rulez.sk/projects/bruteforceblocker/blist.php

### Overview
dangerrulez provide blocklist of Ip used SSH bruteforce attacks via firewall

#### dangerrulez IP feed
This feed includes
Ip used in bruteforce attacks

### PRE-REQUISITES to use dangerrulez feed API and DNIF  
Outbound access required to request dangerrulez feed API

| Protocol   | Source IP  | Source Port  | Direction	 | Destination Domain | Destination Port  |  
|:------------- |:-------------|:-------------|:-------------|:-------------|:-------------|  
| TCP | AD,A10 | Any | Egress	| github.com | 443 |
| TCP | AD,A10 | Any | Egress	| danger.rulez.sk  | 80 | 


### Using the dangerrulez feed API and DNIF
 The dangerrulez feed API is found on github at

https://github.com/dnif/enrich-dangerrulez

#### Getting started with dangerrulez feed API and DNIF

1. #####    Login to your AD, A10 containers  
   ACCESS DNIF CONTAINER VIA SSH : [Click To Know How](https://dnif.it/docs/guides/tutorials/access-dnif-container-via-ssh.html)
2. #####    Move to the ‘/dnif/<Deployment-key/enrichment_plugins’ folder path.
```
$cd /dnif/CnxxxxxxxxxxxxV8/enrichment_plugins/
```
3. #####   Clone using the following command  
```  
git clone https://github.com/dnif/enrich-dangerrulez.git dangerrulez
```
### API feed output structure
  | Fields        | Description  |
| ------------- |:-------------:|
| EvtType      | An IP |
| EvtName      | The IOC      |
| IntelRef | Feed Name      |
| IntelRefURL | Feed URL      |
| ThreatType | DNIF Feed Identification Name |      

An example of API feed output
```
{'EvtType': 'IPv4',
'EvtName': '85.255.1.106',
'AddFields': {
'IntelRef': ['DANGERRULEZ'],
'IntelRefURL': ['http://danger.rulez.sk/projects/bruteforceblocker/blist.php'], 
'ThreatType': ['blacklist'] }}
```
