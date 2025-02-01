
2025-01-17 10:06
Status: 
Tags: #bitcoin #cryptocurrency #blockchain 

## Chapter 1. Introduction
#### What is Bitcoin?
- Collection of concepts and technologies that form the basis of a digital money ecosystem
- Bitcoin are entirely virtual, no physical coins or even digital coins
- Idea is to allow users to transfer value from sender to recipient. 
- Users of bitcoin have keys that allows them to prove ownership of bitcoin in the bitcoin network. These keys can sign transactions to unlock the value and spend it by transferring it to a new owner. 
- Keys are often stored in a digital wallet on each user’s computer or smartphone
- Bitcoin is a **DISTRIBUTED, PEER-TO-PEER** system. 
- There is no “central” server or anyone controlling the entire thing

#### How are bitcoin created?
Through a process called “Mining”
- Involves competing to find solutions to a mathematical problem while processing bitcoin transactions. 
- anyone in the bitcoin network may operate as a miner, using their computer’s processing power to verify and record transactions.
- The bitcoin protocol has built-in algorithms that regulate the mining function across the network. 
#### Digital Currencies before Bitcoin
Questions to ask:
1. Can I trust that the money is authentic and not counterfeit?
2. Can I trust that the digital money can only be spent once?
3. Can I be sure that no one else can claim this money belongs to them and not me?
Early digital currencies actually worked, but they were centralised, and were easy to attack by governments and hackers. To be robust against hackers and other government, it had to be decentralised by design and free of any central authority.

#### History of Bitcoin
Satoshi Nakamoto combined several prior inventions such as b-money and HashCash to create a completely decentralised electronic cash system. This system did not rely on central authority for currency issuance or settlement and validation of transactions. 
- Key innovation was to use a distributed system (“[[Proof-of-Work]]”)
- Idea is to arrive at consensus about the state of transaction. Allowing them to tally and match. 
- Solving the issue of double spending
>[!NOTE]
> In terms of double spending, the issue was solved previously with a clearing house. Think of the SGX as a clearing house. To ensure all transactions are accurate

#### Bitcoin Uses, Users, and Their Stories
- North American low-value retail
- Offshore contract service
	- Payment in Bitcoin
- Import/Export, transfer of money across different regions

#### Choosing a Bitcoin wallet
1. Desktop Wallet
	1. Usually not ran on Windows or Mac, due to the security disadvantages
2. Mobile Wallet
	1. Most common type of bitcoin wallet. Many are designed for simplicity and ease-of-use
3. Web Wallet
	1. Usually stores the user’s wallet on a server owned by a third party. Similar to webmail in that it relies entirely on a third-party server. 
4. Hardware Wallet
	1. Self-contained Bitcoin wallet on a special-purpose hardware. Operated via USB with NFC on a mobile device
5. Paper Wallet
	1. Keys controlling bitcoin can be printed for long-term storage. Offers a low-tech but highly secure means of storing bitcoin long term. Offline storage = Cold storage
6. Stores the entire history of bitcoin transactions, manages users’ wallet and can initiate transactions directly on the bitcoin network. Full-node client consumes substantial computer resources (125GB of disk, 2 GB of RAM)
7. Lightweight Client
	1. Also known as Simple-Payment-Verification (SPV), connects to bitcoin full nodes for access to the bitcoin transaction information
	2. stores the user wallet locally and independently creates, validates and transmit transactions. 

> [!TIP]
> Bitcoin addresses start with a 1 or 3. They can be shared with other bitcoin users who can send bitcoin directly into your wallet. Nothing sensitive. Modern wallets automatically create a new address for each transaction to maximise privacy. A wallet is simply a collection of addresses and keys that unlock the funds within.

After sending bitcoin across, it will remain “Unconfirmed” until it has been recorded in the bitcoin transaction ledger (blockchain). Only when a transaction is included in a block and added to the blockchain. 

This whole process is called “Clearing” in the traditional banking sense

## Chapter 2: How Bitcoin Works
#### Transactions, Blocks, Mining, and the Blockchain
#### Bitcoin Overview
![[Screenshot 2025-01-17 at 13.08.00.png]]

#### Bitcoin Transactions
##### Transaction Inputs and Outputs
- Double entry bookkeeping ledger
- There are one or more “outputs”
	- Inputs do not necessarily add up to the same amount as outputs due to transaction fee, which is a small payment collected by the miner
![[Screenshot 2025-01-17 at 13.14.23.png]]
There is a continuation of payments from one person to another person. The inputs from the latest transaction correspond to outputs from previous transactions. 

In summary, transactions move from transaction inputs to transaction outputs. You may have 20 bitcoins but the payment was only 5 bitcoins, so then there is a change output back to the original owner. Outputs from 1 transaction can be used as inputs in a new transaction. So you get to see the chain of ownership as value is moved.

##### Constructing a Transaction
The wallet application contains all the logic for selecting appropriate inputs and outputs to build a transaction. We as the end user only need to specify a destination and an amount, and the rest happens in the wallet application. 






## References

