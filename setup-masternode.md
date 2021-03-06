## How to setup a DFI-Masternode
Based on: https://defichain.com/learn/run-a-masternode/

### Requirements: 

+ I am not going into details of how to setup a DFI-node._
+ *I am only interesting in the scenario:*
+ + "For owners who would like to delegate the DFI-Masternode duties to another node" as descibed in the link above. As I don't want to store 20k DFI on my server and/or local ´AIN´ instance. 

**Terms:**

We need to define some terms, in order to understand the process of setting up a DFI-Masternode.

+ **Wallet = local DFI-Wallet or AIN (PC)**

This can be any DFI-Wallet you want to use. It could be your local DFI-Wallet or any `ain` you running locally. 

+ **Node =  remote Server for Masternode or local AIN**

If you already have a remote DFI-Node use it as a operator node or you can use your local AIN as well. 

+ **owner address = owner who has the 20.010 DFI on one particular DFI-legacy-address**

What is a legacy address:gar  https://github.com/DeFiCh/ain/wiki/DeFiChain-Address-Format


**Requirements:** 

+ -20.000 DFI + 10 DFI + a few DFI for testing = ~ 20.010 DFI in total. 
+ 1x remote Node  / local AIN
+ 1x local Wallet 

#### 1 
**1. create a legacy address on Wallet:**

I am  adding a label to the generated DFI address "masternode-owner"

`defi-cli getnewaddress "masternode-owner" legacy`

you can also create a legacy address using the GUI and choose `Show advance options` when creating a new address.

#### 2
**2. Fund this new Wallet address with exactly 20.010 DFI.**

#### 3

**3.On your Node:** 

create also a legacy address **We will call it node-address**
_It is called `operator-address` on the official tutorial_

**3.1 edit defi.conf

On your node you need to edit the `defi.conf` file and add to the bottom

```
gen=1
masternode_operator=node-address
```
**3.2 restart node

restart your `defid` 

**3.3 check logs**

If sucessfull you should see something like this in your `debug.log`

```
Log:
2021-03-01T11:49:21Z ThreadStaker (93399bc2b307c82cd21f802c9e20d4899ca1ef7f): waiting init...
```


#### 4

**4 .On your Wallet register a new masternode on the network:**

Please make sure you have 10DFI on the wallet address, as this command will cost 10 DFI in addition to the 20.000 DFIs:

`defi-cli createmasternode wallet-address node-address`

#### 5

**5 . on Wallet**

Edit your `defi.conf` and add `masternode_owner=masternode-owner (dfi-address) ` where  masternode-owner is the legacy address we created on our wallet called "masternode-owner".



When using an `ain` there is no need for `gen=1` on the wallet `defi.conf`

#### 6

**6 . restart node** 

## if sucessfull 

If everything was successfull you should see on your DFI-Wallet:

![DFI Masternode view in Wallet](https://github.com/AltCoiFish/dfi-masternode/blob/main/Wallet-masternode-view.png?raw=true)
