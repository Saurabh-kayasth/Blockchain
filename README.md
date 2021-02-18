# Blockchain
## 1 : What is Blockchain ? 
Definition : A blockchain is a continuously growing list of records called blocks, which are linked and secured using cryptography.

### Block
* First block is called Genesis Block 
* It doesn't have a previous hash, because it is the first block in the chain and there is no block before the first block.
* It has its own hash.
* After the first block every block has a previous hash and its own hash and thats how the link is made between blocks.
* The blocks are cryptographically linked with each other.
* Hash is made using data (block no.,previous hash, data etc.) in a particular block.
* A block holds multiple transactions.
* What constitutes a block : 
  * Data : String, number etc.
  * Value - Previous hash
  * Hash - Its own hash

## 2 : Understanding SHA256 Hash :
* A fingerprint that identifies a digital document.
* It is one of the core principles of building blocks in blockchain.
* SHA -> Secure Hash Algorithm
* 256 -> Number of bits it takes up in memory
* The hash is always 64 characters long
* A character is basically in Hex format ( 0 to F ).
* Each Hex character consists of 4 bits, so 64x4  = 256 bits.
* 5 Requirements for hash algorithm : 
  * One-way : You can not go from hash to document
  * Deterministic : Same document should result in same hash
  * Fast computation
  * The Avalanche Effect
  * Must withstand collisions : limited hash
* Visualize:  https://tools.superdatascience.com/blockchain/hash/
  * Slight change in data changes the hash completely ( avalanche effect )
  * For same data hash is same ( as every person has same fingerprint )
  * No matter how big the data is, hash is going to be 64 characters long only i.e 256 bits.

## 3 : Immutable Ledger
### Traditional Ledger : 
* Property entries are used to write in a register or digitally ( computer ).
* Information of who owns what. 
* Also it’s practically impossible to know which property belongs to who if some disaster happens.
* If entries are made in a register or even in a computer (excel sheet), it's really not hard to manipulate those entries. So to solve this problem blockchain comes into picture. 
### Blockchain
* Suppose those property entries are made using blockchain, then even if someone tries to manipulate the block he will have to change the hash of every block which is added after that block.
* So, practically it’s impossible to change blocks in the chain.

## 4 : Distributed P2P Network
* Even if the property entries are made using blockchain, somebody can come in and spend some time and change the blocks ( although it’s a time consuming process but not impossible ).
* Also something might happen in the middle of the chain accidentally then how would you restore it ?
* These are some of the problems which Distributed P2P Network solves.
* In P2P Blockchain is copied all across the computer.
* Once a new block is added into a network, then that information is broadcasted throughout the network and a new block is added on each computer in a network.
* This process might take some time.
* Blockchains on different computers(peers) are synced regularly. So, even if an attacker is able to make some changes on one computer, the other computer’s blockchain won’t match that computer.
* So, it's practically impossible for an attacker to successfully change the blockchain.
* Other peers in a network will have different blockchain, except the one which has been hacked. So with majority other peers will form consensus and their blockchain will get copied to the computer which has been hacked.
* That's how we bring trust in peers.
* So to successfully attack on a blockchain the attacker will have to attack on more than 50% of the computers at the same time ( to make majority consensus ).
* The more number of peers , the harder it is possible to attack.

## 5 : How mining works ( Nonce )
To compute a hash for a particular block we take block no, previous hash, and data. So,
What's the whole fuss about mining ?
Why are there so many mining rigs around the world ?
Why is lots of computation power dedicated to a computer ?
What’s the competition that everybody is in ?
So, there is another field in the block which is known as Nonce.
* Nonce : Number Used only once
* This field is what mining is all about. Miners change this field only, for mining.
* Nonce is mutable, we are freely allowed to change it.
* So basically nonce allows us to vary the Hash.
* A small change in nonce changes the hash completely.

## 6 : How mining works ( The cryptography puzzle )
* A Hash is a number.
* The blockchain algorithm sets the target for miners to accomplish a certain hash to create a block.
* Any Hash above the target is not accepted.
* This is a completely arbitrary process.
* As in a block Nonce is mutable, so miners basically change the nonce until they find a nonce that generates Hash below the target Hash.
* Once they (miners) find a required Nonce the new block is added and they get some reward.
* As small change in nonce changes the Hash completely, so if changing the nonce world change little bit hash then the miners would know in which order (increasing/reducing) they have to change the nonce and because of that not every miner will get a chance of mining a block, which will not let them to win a reward.
* Mining is all about solving cryptographic puzzles, and it needs lots of work, computing resources, electricity etc. On the other hand verifying a block is an easy process, it just needs data to generate Hash and after generating Hash it can be used to verify if the block is valid or not.
