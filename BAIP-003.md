<pre>
  BAIP: 003
  Layer: Consensus 
  Title: Pay to Script Hash Changes
  Author: Aleksey Karpov admin@bitcoinasset.org
  Comments-Summary: No comments yet.
  Status: Draft
  Type: Standards Track
  Created: 2017-09-25
</pre>

Abstract
--------
This BAIP describes changes for P2SH in Bitcoin Asset inherited from Bitcoin BIP 16.

Motivation
----------
In connection with the changes changes introduced in BAIP 002 we need to redefine pay-to-script-hash.

Specification
-------------
A new standard script corresponds to transaction output script version 2 and 3:

_`OP_HASH160 [20-byte-hash-value] OP_EQUAL`_  [2]

[20-byte-hash-value] shall be the push-20-bytes-onto-the-stack opcode (0x14) followed by exactly 32 bytes. Hash value calculated first with RIPEMD-160.



_`OP_HASH256 [32-byte-hash-value] OP_EQUAL`_ [3]

[32-byte-hash-value] shall be the push-32-bytes-onto-the-stack opcode (0x14) followed by exactly 20 bytes. Hash value calculated  with SHA-256.

Hash used in both types of script calculated from Merkle Root of Merkle tree that encodes mutually exclusive branches in a redeem script. When spending the redeemer provide the branch they are executing, and hashes that connect the branch to the Merkel root.

To redeem an P2SH output, the signature script must consist of the following items:

_`<Signatures> <Path> <Serialized Script>`_

_Path_ it is a serialized Merkle path. Size of Path must be a multiple of 32 bytes, and not more than 1024 bytes. Depth of the tree (0 to 32) is the size of Path divided by 32. Each 32 byte word is a SHA256 merkle node. The script evaluation fails if Path is not connected to Merkle root.

The script fails with one of the following conditions:


*  Path is not connected to Script Merkle root.
*  Size of any one of the script branch item is larger than 520 bytes.
*  Number of non-push operations (nOpCount) of the script branch is more than 201. 

<img src="https://github.com/bitcoinAsset/BAIP/blob/master/BAIP-003/baip-003-1.png" width="604" height="345">


## References 

https://github.com/bitcoin/bips/blob/master/bip-0016.mediawiki

https://github.com/bitcoin/bips/blob/master/bip-0114.mediawiki


## Copyright 

This document is placed in the public domain.
