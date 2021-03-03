**DRAFT **

**How to setup a DFI-Masternode**

**I am not going into details of how to setup a DFI-node.** 

**Based on:**  https://defichain.com/learn/run-a-masternode/

I am only interesting in "For owners who would like to delegate the masternode duties to another node" because I don't want to store 20k DFI on my Server. 

In the following steps I will try to describe a way for the `block 678,000 on 01 March 2021 Dakota-Upgrade` .


**Terms:**

+ **Wallet = local DFI-Wallet or AIN (PC)**

(This can be any DFI-Wallet you want to use) 

+ **Node =  remote Server for Masternode or local AIN**

(if you already have a DFI-Node use it as a operator node or you can use your local AIN)

+ **owner address = owner who has the 20.000 DFI on one particular DFI-legacy-address**


**Requirements:** 

+ -20.000 DFI + 10 DFI + a few DFI for testing = ~ 20.010 DFI in total. 
+ 1x remote Node  / local AIN
+ 1x local Wallet 

**1. create a legacy address on Wallet:**

I am  adding a label to the generated DFI address "masternode-owner"

`defi-cli getnewaddress "masternode-owner" legacy`

you can also create a legacy address using the GUI and choose `Show advance options` when creating a new address.

**2. Fund this new Wallet address with exactly 20.010 DFI.**


3.
**On your Node:** 

create also a legacy address **We will call it node-address**
_It is called `operator-address` on the official tutorial_

**3.1

On your node you need to edit the `dfid.conf` file and add to the bottom

```
gen=1
masternode_operator=node-address
```
**3.2

restart your `defid` 

**4 .
On your Wallet register a new masternode on the network:**

Please make sure you have 10DFI on the wallet address, as this command will cost 10 DFI in addition to the 20.000 DFIs:

`defi-cli createmasternode wallet-address node-address`

**5 . on Wallet edit your** `defi.conf` and add `masternode_owner=masternode-owner` and `gen=1`  where wallet-address is the legacy address we created on our wallet called "masternode-owner"

**6 . restart node** 

**## if sucessfull 

If everything was successfull you should see on your DFI-Wallet:


