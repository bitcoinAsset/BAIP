<pre>
  BAIP: 001
  Layer: Consensus 
  Title: New Transaction structure
  Author: Aleksey Karpov admin@bitcoinasset.org
  Comments-Summary: No comments yet.
  Status: Draft
  Type: Standards Track
  Created: 2017-09-22
</pre>

Abstract
--------

Bitcoin Asset protocol is based on the Bitcoin protocol, this BAIP describes modifications to the Bitcoin protocol transaction structure.

Motivation
----------
Segregated Witness required Bitcoin to run softfork. On start a new Bitcoin Asset blockchain, we will apply changing the transaction structure.



Specification
-------------

### Transaction ID

Recent transaction txid serialization format: the double SHA256:

_`txid = SHA256 ( [nVersion] [[inputPoint][signatureScript][sequence]] [txouts] [nLockTime] )`_
    
New transaction txid serialization format: 

_`txid = SHA256 ( [nVersion] [[inputPoint] [sequence]] [txouts] [nLockTime] )`_

[signatureScript] excludes from serialization

A new wtxid is defined as old txid format:

_`wtxid = SHA256 ( [nVersion] [[inputPoint][signatureScript][sequence]] [txouts] [nLockTime] )`_


### Transaction output

Old Transaction out  format:

_`[amount] [script]`_

New Transaction out  format:

_`[assetID] [amount] [scriptVersion] [script]`_

Bitcoin use only single asset inside blockchain. Bitcoin Asset give ability to use a bunch of assets, A new **assetID** field defined - varInt value not more then 9 bytes.

All standard transaction types defined by **scriptVersion**:


|   Version |  Script                     | Note |
| --------- | ----------------------------| -----|
|    0      | Pure script                 | Not relayed by nodes |
| 1 | 20 bytes Public Key RIPEMD160 hash| replaced with P2PKH script on verification |
|2 | 20 bytes Script RIPEMD160 hash | replaced with P2SH script on verification |
|3 | 32 bytes Script SHA256 hash |  replaced with P2SH script on verification |
|4 | up to 80 bytes message | only 1 output per transaction allowed |

In case **scriptVersion** higher then known versions, transaction will not relayed, on execution script successfully passes the verification.




