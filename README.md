# DudgX
Shell script to install a [DudgX Masternode](https://www.dunderdogcoin.com/) on a Linux server running Ubuntu 16.04.
***

## VPS installation
```
wget -N https://raw.githubusercontent.com/DUDGdev/DudgX-Masternode-Script/master/dudgxmn_install.sh
bash dudgxmn_install.sh
```
***

## Desktop wallet setup

After the Masternode is up and running, you need to configure the desktop wallet accordingly. Here are the steps:
1. Open the DudgX Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **50000** DUDGX to **MN1**. You need to send all 50000 coins in one single transaction.
4. Wait for 15 confirmations.
5. Go to **Help -> "Debug Window - Console"**
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
startmasternode alias 0 MN1
```
14. Login to your VPS and check your masternode status by running the following command to confirm your MN is running:
```
DudgX-cli masternode status
```
***

## Usage:
```
DudgX-cli masternode status #To check your MN status
DudgX-cli getinfo #To get general info such as DudgX version and current block numnber
DudgX-cli mnsync status #To check if your MN is synced.
```
Also, if you want to check/start/stop **DudgX**, run one of the following commands as **root**:

```
systemctl status DudgX #To check if DudgX service is running
systemctl start DudgX #To start DudgX service
systemctl stop DudgX #To stop DudgX service
systemctl is-enabled DudgX #To check if DudgX service is enabled on boot
```
***

## Donations
Any donation is highly appreciated

**BTC**: 1KWC1RXFrFjnCEF684o3kpDwtTLiMBbsqf
**ETH**: 0x94E27a1DF0fbc3E694c8B995EBF7F75277cAe7fd
