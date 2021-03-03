**DRAFT **

**How to setup a DFI-Masternode**

**I am not going into details of how to setup a DFI-node.** 

**Based on:**  https://defichain.com/learn/run-a-masternode/

I am only interesting in "For owners who would like to delegate the masternode duties to another node" because I don't want to store 20k DFI on my Server. 

In the following steps I will try to describe a way for the `block 678,000 on 01 March 2021 Dakota-Upgrade` .


**Terms:**

+ **Wallet = local DFI-Wallet or AIN (PC)**
(This can be any DFI-Wallet you want to use) 

+ **Node =  remote Server for Masternode**
(if you already have a DFI-Node use it as a masternode)

+ **owner address = owner who has the 20.000 DFI on one particular DFI-legacy-address**


**Requirements:** 

+ -20.000 DFI + 10 DFI + a few DFI for testing = ~ 20.030 DFI in total. 
+ 1x remote Node  
+ 1x local Wallet 

**1. create a legacy address on Wallet:**

I am not adding a label, therefore "" you could do "my_first_masternode" as a label, but this is not important. **We will call it wallet-address**

`defi-cli getnewaddress "" legacy`

**2. Fund this new Wallet address with 20.010 DFI.**

3.
**On your Node:** 

create also a legacy address **We will call it node-address**

**4 .
On your Wallet register a new masternode on the network:**

Please make sure you have 10DFI on the wallet address, as this command will cost 10 DFI in addition to the 20.000 DFIs:

`defi-cli createmasternode wallet-address node-address`

**5 . on Node edit your** `defi.conf` and add `masternode_owner=wallet-address` and `gen=1`  where wallet-address is the legacy address we created on our wallet. 

**6 . restart node** and a as a good practise restart wallet as well prior to restart node.*
