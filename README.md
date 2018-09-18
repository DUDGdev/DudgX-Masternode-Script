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
10. Go to  **Tools -> "Open Wallet Configuration File"**
11. Insert the following into that file:
```
rpcuser=AnyUsername
rpcpassword=Any Password
txindex=1
listen=1
server=1
daemon=1
logtimestamps=1
maxconnections=256
masternode=1
masternodeprivkey=Masternode Private Key
masternodeaddr=VPS IP:38349
```
12. Save and close the file.
13. **Restart your wallet**
14. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
15. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
16. Select your MN and click **Start Alias** to start it.
17. Alternatively, open **Debug Console** and type:
```
startmasternode alias 0 MN1
```
18. Login to your VPS and check your masternode status by running the following command to confirm your MN is running:
```
Dudgx-cli masternode status
```

***

## Usage:
```
Dudgx-cli masternode status #To check your MN status
Dudgx-cli getinfo #To get general info such as DudgX version and current block numnber
Dudgx-cli mnsync status #To check if your MN is synced.
```
Also, if you want to check/start/stop **Dudgx**, run one of the following commands as **root**:

```
systemctl status Dudgx #To check if DudgX service is running
systemctl start Dudgx #To start DudgX service
systemctl stop Dudgx #To stop DudgX service
systemctl is-enabled Dudgx #To check if DudgX service is enabled on boot
```
***
Any donation is highly appreciated

BTC   394CVEQbp1TVvKXh9GNjd8nzPS2BNzsast
DUDGX DGbSaLiChdSqsz1RQ8zwS51RM2BSdgfPCJ
