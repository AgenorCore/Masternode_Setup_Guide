# AGENOR
Shell script to install a [ Masternode](https://agenorcoin.com/) on a Linux server running Ubuntu. Use it on your own risk.
***

## Installation
```
In case of ubuntu18.0.4 :

wget https://raw.githubusercontent.com/AgenorCore/Masternode_Setup_Guide/main/install-MN-18.0.4.sh
bash install-MN-18.0.4.sh

***********************************

In case of ubuntu16.0.4 :

wget https://raw.githubusercontent.com/AgenorCore/Masternode_Setup_Guide/main/install-MN-16.0.4.sh
bash install-MN-16.0.4.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Agenor Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **10000** AGE to **MN1**. You need to send all 10000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **getmasternodeoutputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
startmasternode alias false "MN1"
```
14. Login to your VPS and check your masternode status by running the following command:.
```
agenor-cli getmasternodestatus
```
***

## Usage:
```
agenor-cli mnsync status
agenor-cli getmasternodestatus  
agenor-cli getinfo
```

***
