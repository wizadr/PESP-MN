# PESPCOIN Masternode Setup 
This guide will assist you in setting up a PESPCOIN Masternode on a Linux Server running Ubuntu 16.04 / 18.04

- [PESPCOIN Masternode Setup](#pespcoin-masternode-setup)  
  	* [Requirements](#requirements) 
  * [Connecting to the VPS and installing the masternode script](#Connecting-to-the-VPS-and-installing-the-masternode-script)  
         [1. Log into the VPS with **root**](#1-log-into-the-vps-with-root)  
         [2. Git Installation](#2-git-installation)  
         [3. Clone MN setup script](#3-clone-mn-setup-script)  
         [4. Start MN setup script](#4-start-mn-setup-script)  
         [5. Copy Masternode Private Key](#5-copy-masternode-private-key-from-vps-console-window-and-pres-enter)
  * [Setup QT wallet](#setup-qt-wallet)  
         [1. Create new receiving address and copy it](#1-create-new-receiving-address-and-copy-it)  
	 [2. Send Collateral amount of PESPCOIN to copied address](#2-send-collateral-amount-of-pespcoin-to-copied-address)  
	 [3. Get MN output and Set Masternode Configuration File](#3-open-console-get-mn-output-and-set-masternode-configuration-file-and-save-it)  
	 [4. Wait at least 15 confirmation of transaction](#4-wait-at-least-15-confirmation-of-transaction)  
         [5. Restart QT wallet](#5-restart-qt-wallet)  
         [6. Start MN in QT wallet console](#6-start-mn-in-qt-wallet-console)  
	 [7. Check Masternode Status in VPS](#7-check-masternode-status-in-vps)  

## Requirements
- MN Collateral(10,000 PESP) amount of PESPCOIN.
- A VPS running Linux Ubuntu 16.04 or 18.04 with 1 CPU & 1GB Memory minimum (2gb Recommended) from [Vultr](https://www.vultr.com/?ref=8622028) or any other providers.
- PESPCOIN Wallet (Local Wallet)
- An SSH Client (<a href="https://www.putty.org/" target="_blank">Putty</a> or <a href="https://dl.bitvise.com/BvSshClient-Inst.exe" target="_blank">Bitvise</a>)


## Connecting to the VPS and installing the masternode script

##### 1. Log into the VPS with **root**  
[![Vps](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/1.png)]
***
##### 2. Git Installation:  
- ```sudo apt-get install -y git-core```  

[![Git](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/2.png)]
***
##### 3. Clone MN setup script: 
- ```git clone https://github.com/PESPCOIN/PESP-MN.git```  

[![Script1](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/3.png)] 
***
##### 4. Start MN setup script:
##### For Ubuntu 16.04
- ```cd PESP-MN && chmod +x ./PESP-16.04-MN.sh && ./PESP-16.04-MN.sh```

##### For Ubuntu 18.04
- ```cd PESP-MN && chmod +x ./PESP-18.04-MN.sh && ./PESP-18.04-MN.sh```
   
[![Script2](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/4.png)]  

##### 5. Now ask for VPS Public IP Address** 
[![Script3](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/5.png)]

**Now you need to wait some time, while script preparing the VPS to setup**  
***
##### 6. Copy masternode private key from VPS console window and pres "Enter":
[![Download Bitvise](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/6.png)] 

- if you see this, you are on the right track:
[![QT1](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/7.png)]

- to check VPS daemon status, type: ```PESPCOIN-cli getinfo```
[![QT2](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/8.png)]

**Don't close this window!** 	
***

## Setup QT wallet
##### 1. Create new receiving address and copy it
[![QT3](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/9.png)] 

***
##### 2. Send Collateral amount of PESPCOIN to copied address
[![QT4](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/10.png)]
***
##### 3. Open console Get MN output and set masternode configuration file and save it
- ```mn1 VPS_IP:9599 masternode_genkey masternode_output output_index```:
[![QT5](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/11.png)]
***
##### 4. Wait at least 15 confirmation of transaction

##### 5. Restart QT wallet  
- **it's important**

##### 6. Start MN in QT wallet console:
- ```masternode start-alias TEST-MN```
[![QT7](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/12.png)]
***
##### 7. Check Masternode Status in VPS:
- ```PESPCOIN-cli masternode status```  
[![QT8](https://raw.githubusercontent.com/PESPCOIN/PESP-MN/main/assets/13.png)]  

**It will gives you output and status like "Masternode successfully started"** 	
***
**Сongratulations you did it!**