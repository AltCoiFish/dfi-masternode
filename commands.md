## Useful commands for DFI-Masternodes

+ List all DFI-Masternodes

`defi-cli listmasternodes`

**Output:**

```
},
  "416ee97b56f6ea5c72cd1d9daa29571346ba01560ed23f82fbfd4a624fa6db05": {
    "ownerAuthAddress": "8QYrDP3eKPdoo1gxRJr5FbzUPm1DxiDvxh",
    "operatorAuthAddress": "8Xh5tcoAdjP69Svfz9zcFW1YsymyvQRYku",
    "creationHeight": 3171,
    "resignHeight": 201675,
    "resignTx": "de0c2417a5b9437bbd290712020f3950d805c368ef23aeaf2e3efbaf9fa87140",
    "banHeight": -1,
    "banTx": "0000000000000000000000000000000000000000000000000000000000000000",
    "state": "RESIGNED",
    "mintedBlocks": 311
  },
  "80b58d17c558c4f62ce8f399469fa914ba33e8f9a645e873ddbcdb40ab21f205": {
    "ownerAuthAddress": "8K8TiY1VL6dtSpRf1AweZTA9a5yQ48arBF",
    "operatorAuthAddress": "8RnEh7MhdATAd25BjnU7AsAKMvNY2yJVzR",
    "creationHeight": 682738,
    "resignHeight": -1,
    "resignTx": "0000000000000000000000000000000000000000000000000000000000000000",
    "banHeight": -1,
    "banTx": "0000000000000000000000000000000000000000000000000000000000000000",
    "state": "ENABLED",
    "mintedBlocks": 0
  },


```
+ List only your DFI-Masternode based on id
 
`defi-cli getmasternode "80b58d17c558c4f62ce8f399469fa914ba33e8f9a645e873ddbcdb40ab21f205"`

**Output:**

```
{
  "80b58d17c558c4f62ce8f399469fa914ba33e8f9a645e873ddbcdb40ab21f205": {
    "ownerAuthAddress": "8K8TiY1VL6dtSpRf1AweZTA9a5yQ48arBF",
    "operatorAuthAddress": "8RnEh7MhdATAd25BjnU7AsAKMvNY2yJVzR",
    "creationHeight": 682738,
    "resignHeight": -1,
    "resignTx": "0000000000000000000000000000000000000000000000000000000000000000",
    "banHeight": -1,
    "banTx": "0000000000000000000000000000000000000000000000000000000000000000",
    "state": "ENABLED",
    "mintedBlocks": 0
  }
}
```

+ Check if you masternode is mining

`defi-cli getmintinginfo` 

**Output:**

```
{ 
  "blocks": 682941,
  "currentblockweight": 5758,
  "currentblocktx": 2,
  "difficulty": 364273275.7898824,
  "isoperator": true,
  "masternodeid": "80b58d17c558c4f62ce8f399469fa914ba33e8f9a645e873ddbcdb40ab21f205",
  "masternodeoperator": "14ba33e8Eh7MhdATAd25BjnU7AsAKMvNY2yJVzR",
  "masternodestate": "ENABLED",
  "generate": true,
  "mintedblocks": 0,
  "networkhashps": 2.465515082987458e+16,
  "pooledtx": 2,
  "chain": "main",
  "warnings": ""
}
```
