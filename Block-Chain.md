**Block Chain**

```
Module1: 
Block chain Intuition
Create a Blockchain
Module2A: Cryptocurrency Intuition
Module2B: Cryptocurrency Transaction
Module2: Create a Cryptocurrency
Module3: smart contract intuition

goal: consulting business on blockchain/ apply block chain in your own work

https://www.investopedia.com/terms/b/blockchain.asp
https://www.superdatascience.com/podcast/podcast-rise-of-blockchain
https://www.superdatascience.com/pages/blockchain

Section3:
Blockchain Intuition:
Plan of Attack:

what is bockchain?
Understanding SHA256 Hash
Immutable Ledger
Distributed Peer to Peer Network
How Mining works(part1: the Nonce)
How Mining Works(Part2: The cryptographic Puzzle)
Byzantine Fault tolerance
Consensus Protocol(Defence against attackers)
Consensus Protocol(Competing chains)
Blockchain demo


what is blockchain?
how to timestamp a digital document
a continuously growing list of records, called blocks, which  are linked and secured using cryptography.

Data of the block
Previous Hash
its own Hash
hash is a like fingerprint of the data containing within the  block.


first block will not have previous hash

blocks are cryptographically linked to each other through hashes


video9: Understanding SHA256-Hash
similar to finger print is identification of a person
for digital documents it is SHA256, algo behind SHA256 is developed by NSA, this algo is very secure to store passwords, documents etc. it is building block of blockchain.


what is the algorithm of SHA256?
SHA256: SHA-Secure Hash Algorithm, 256 is no of bits it takeup in the memory.  Hash is 64 characters long, it is hexadecimal algorithm comibination of digits and alphabets.

each character takes up 4 bits.

http://tools.superdatascience.com/blockchain/hash/

7:00
https://edgeverve.udemy.com/course/build-your-blockchain-az/learn/lecture/9657366#overview



Five requirements of Hash Algorithms?
One-Way: you cannot go from hash to document/ restore the document from hash.
Deterministic: should always generate same hash for given document when generated multiple times
Fast computation:
The avalanche Effect: tiny change of the document also should generate a different hash.
Must Withstand Collisions: 




Additional Reading:
On the secure Hash Algorithm family(Chapter1 of Cryptography in Context)

Wouter Penard & Tim van
Werkhoven(2008)

https://www.staff.science.uu.nl/~tel00101/liter/Books/CrypCont.pdf

video10: Immutable Ledger
blocks are cryptographically linked together

video11:
distributed p2p network:



link: https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274

video12:
How mining works: The Nonce

each block in blockchain contains following:
blockno
data that block needs to hold(a block can hold multiple transactions)
Hash of Previous block
Hash of current block(generated based on the data that block is holding)
Nonce: Number used only once(this field is the mining all about)

what is that now controls the hash of current block:
blockno
nonce
data
prevHash



Nonce gives extra control to manipulate the hash of the block
We cannot change other fields as it results in tampering of the data defeats the purpose of block chain, so nonce gives extra control to change the hash of the block


video13:
How Mining works: The cryptographic puzzle

A hash is a hexa decimal number
64 digit character length
each of 4 byte..so overall 256 bytes..so SHA256

block chain sets a traget for minners to accomplish a hash, the way it works any value higher than target doesn't work.
there is no economical reason for it..its just a way to put hurdles or challange for minners in minning the block



Minners change the field of nonce to try guessing the hash to make sure they reach the target given to them
if they are able to generate a hash below the target then they are won.


10:00


why do we need nonce for minning is to keep people from cheating the system

the reason for using sha256 is we cannot predict the algorithm. predicting the nounce is the only way to find the hash, there are previous hash algorithm like SHA1, MD5, MD4 which have been cracked but everything they get updated and SHA256 is only used in blockchain.


you need to keep chainging the nounce until you get a hash below target


video14: Byzantine Fault Tolerance
it is important not only for block chain but also for any decentralized system

https://medium.com/loom-network/understanding-block-chain-fundamentals-part-1-byzantine-fault-tolerance-245f46fe8419


video15:
Consensus protocol: Defence Against Attackers

solves two problems:
protect network from attackers
competing chains: two chains can compute the block at almost same time

different types of consensus protocols:
Proof of work(PoW): 
Proof of Stake(PoS)
Other



ethurium/bitcoin uses PoW

https://tools.superdatascience.com/blockchain/block
https://tools.superdatascience.com/blockchain/hash

Section4:
Create a block chain

step1:
Module1: Create a blockchain
Module2: Create a cryptocurrency
Module3: Create a smart contract


install anaconda
install flask
install postman


video26: Mining Block chain


Welcome to Part 2 - Cryptocurrency
Welcome to Part 2!

In this Part you will:

Build up a solid Cryptocurrency Intuition
Reinforce this Intuition by understanding in depth Cryptocurrencies transactions
Learn how to create a Cryptocurrency from scratch


Section6: Cryptocurrency Intuition
video35:

what we will learn in this section:
What is bitcoin?
we will get a bird's eyeview of whole crypto space in general.
we will see three different layers:
technology layer
protocol layer
token layer

what different protocols exist, why bitcoin is a protocol
difference between different coins and tokens etc.

lot of foundational things that give us right start for rest of the whole course

bitcoin's monetary policy
Understanding Mining difficulty
Virtual tour of a bitcoin mine
Mining pools
Nonce Range
How Miners Pick transactions(part1)
How Miners Pick transactions(part2)
CPUs vs GPUs vs ASICs
How do mempools work?
Orphaned blocks
The 51% Attack
Extra: Bits to Target Conversion


video36: What is bitcoin?
In crypto world there are 3 important layers
Technology: blockchain
Protocol/COIN: Bitcoin(it is not just a coin or currency, it is actually a protocol)
Token: ICO are tokens

what is protocol:
Protocol is set of rules or guidelines that guides how participants over network communicate with eachother.

ex: tcp, ip,http are protocols which allow how participants over the network to communicate withh each other.


other protocols are:
waves
ethereum: more popular for creating contracts and tokens. it has hundreds of tokens.
neo
ripple
bitcoin cash
zcash
manero

bitcoin doesnot support tokens and contracts.
ripple also don't have tokens
neo has tokens
waves have couple of tokens


Protocol contain within in them an important feature that is coin. 

every protocol has a coin and it is an innate assest of the protocol which facilitates the interaction with players like rewarding players for minning, purchase things from each other.


bitcoin is taking block chain from theory and implementing it practically, so that network of people can transact with each other using this technology. so no need of intermediatary between them like banks are not needed.

this removes banks from middle. 

bitcoin ecosystem:
Nodes: People who want to do transactions
Miners: helps blockchain to grow by mining it and adding transaction into blocks
Large miners: makes large contributions to growth of the chain.

Mining pools: as miners work together in mining process.

 bitcoin is one protocol helps in building the block chain

 https://bitcoin.org/bitcoin.pdf

 video37: Bitcoin's Monetary Policy
The Halving:
No of bitcoins released into the system are halved for every 4 years. ie for every 210000 blocks

monitory policy of bitcoin is completely controlled by the underlying algorithm software. it is not someone going to change as per their requirement.

as time increase reward decreases and fees increasess
mining incentives remain constant

bitcoin is a deflatiory type of currency

Block Frequency:
how often blocks come in to gain the reward.
average block time coin
10 mins bitcoin
15 sec  ethereum
3.5 sec ripple
2.5 min litecoin



video38: Understanding mining difficulty
what is the current target and how does that feel ?
How is mining difficulty calculated?

see the video again

video39:
virtual tour of bitcoin mine


video40: Mining Pools
https://www.kraken.com/
https://slushpool.com/en/story/
https://v3.antpool.com/home
https://www.buybitcoinworldwide.com/mining/pools/



nounce is a 32 bit number which can range upto 4 billion values

```



