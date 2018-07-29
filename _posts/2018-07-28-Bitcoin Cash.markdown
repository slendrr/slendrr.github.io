---
layout: post
permalink: /bitcoincash
title:  "Bitcoin Cash"
date:   2018-07-28 00:00:00 +0000
categories: coinblog
image: bch
desc: A peer-to-peer electronic cash system. Block-size matters. Bitcoin Cash (BCH).
---
Website: <a href="https://bitcoincash.org">https://bitcoincash.org</a><br>
Whitepaper: <a href="https://www.bitcoincash.org/bitcoin.pdf">https://www.bitcoincash.org/bitcoin.pdf</a>

<h2>Mission</h2>
To allow peer-to-peer online payments without a trusted third-party by forming a decentralized network of miners, incentivized to maintain an honest chain of transaction blocks.

<h2>Overview</h2>
Genesis block: January 2009<br>
Fork Date: August 1st 2017<br>
First Block: #478559<br>
Block explorer: <a href="https://blockdozer.com">https://blockdozer.com</a><br>
Supply limit: 21,000,000 BCH<br>
Issuance: Block reward<br>
Block confirmation: Proof-of-Work<br>
Mining algorithm: SHA-256<br>
Block size: 8mb<br>
Developments: Graphene, Gigablock Testnet Initiative, Colored Coins

<h2>Summary</h2>
Bitcoin Cash is a hardfork of the original Bitcoin. When the Bitcoin community disagreed on how to scale and handle the growing number of transactions, they split into two groups. One group stayed with the 1mb block-size and maintained the Bitcoin name. Another group decided to increase the block-size and adopt the name 'Bitcoin Cash'. Bitcoin Cash does not have replace-by-fee, SegWit, or the Lightning Network. All other elements of Bitcoin Cash remain the same as the original Bitcoin. This post will only focus on the differences.

<b>Hardforks</b> occur when a network decides to change its protocol. In the case of Bitcoin Cash, the network decided to increase the block-size of Bitcoin's protocol. As a result, all subsequent blocks mined on the new client are incompatible with blocks mined on the original client. A hardfork in the blockchain is created, with each group of miners mining separate, incompatible blockchains.

<b>Block-size</b> determines how many transactions can be included in a block. When a block is full, outstanding transactions will have to wait for the next block in order to be added to the blockchain. These are called unspent transactions and will collect in the network's memory pool. Transactions in the memory pool are prioritzed based on transaction fees and time of broadcast. Users can pay higher transaction fees to increase the priority of their transactions. The higher fee incentivizes miners to include their transactions first and earn more transaction fees for mining the block. If more transactions are broadcasted faster than the network can confirm them, the memory pool of unspent transactions begins to grow, confirmation times take longer, and transaction fees increase.

Increasing the block-size is a straight-forward way to handle more transactions, but it does come with setbacks. Bigger blocks causes the size of the blockchain to grow faster and storing a copy of the blockchain on a full node will require more storage space. Bigger blocks also hold longer lists of transactions and take longer to propagate throughout the network, requiring more bandwidth and reducing network efficiency. Increasing block-size to scale Bitcoin Cash relies on Moore's Law and the advancement of technology to solve these problems.

<b>Zero-confirmation transactions (0-Conf)</b> can be considered an instant transaction if a receiver can accept the risk for a double-spend attack. The simplest way to perform a double-spend is to broadcast two conflicting transactions. Whichever transaction propagates throughout the network and becomes confirmed first will invalidate the other. Technically, all 0-conf transactions can be double-spent this way, but earlier transactions will have more time to propagate to more nodes and has a higher likelyhood of being confirmed. A more reliable attack would be to pre-mine a transaction first, broadcasting a second 'false' transaction, and then releasing the pre-mined block to invalidate it. This requires more resources, since the attacker would also have to be a miner. The most powerful double-spend attack requires 51% of all mining power in the network, which would basically grant complete control over the blockchain. This requires an enormous amount of resources or collusion between miners and would compromise the entire network.

All forms of payment carries similar types of risk. Accepting cash risks accepting counterfeit bills. Accepting credit cards risks chargebacks or credit card fraud. Accepting zero-confirmation transactions in Bitcoin Cash risks a double-spend attack. Depending on the value of the transaction, it is up to the receiver to determine how much risk they can accept and how many confirmations is required to mitigate that risk.

<h2>current Developments</h2>

<b>Graphene</b> is a protocol for block propagation using set reconciliation. Normally, when network nodes receive transactions and build a block, they must propagate the list of transactions to the rest of the network to make sure the entire network is updated. Faster block propagation increases security and reduces the chance for slower nodes to waste processing power working on outdated blocks. Graphene accomplishes this by encoding the transactions list using a 'Bloom filter' to create an 'Invertible bloom lookup table (IBLT)'.

Basically, the list of transactions is compressed into a much smaller, invertible data set. The key here is the word 'invertible', which means the compressed and filtered transaction list can be reversed. The filtered data is reduced to roughly 10% of the orignial size, allowing must faster propagation throughout the network. Nodes can receive this data set and easily reverse the filter to receive the full transaction list. This improvement greatly reduces the bandwidth requirements and enables scaling Bitcoin Cash with increased block-size. The official whitepaper for Graphene can be found <a href="http://forensics.cs.umass.edu/graphene/graphene-short.pdf">here</a>.

<b>Gigablock Testnet Initiative</b> explores the possibility and implications of running the Bitcoin Cash network with 1GB blocks. The purpose of this project is to find out if a network of this scale is actually viable. If there are problems, then the researchers can brainstorm ideas in advance and begin developing solutions today. The goal is not to implement 1GB blocks immediately, rather it is just an exercise to further test big block scaling.

<b>Colored Coins</b> is a way for users on the Bitcoin Cash blockchain to issue their own coin on the network. Similar functionalities are already available in other cryptocurrencies, often referred to as digital tokens or digital assets. The idea is to 'color' some BCH that you own with a cryptographic tag. The BCH you've tagged can be spent as a regular BCH coin as well as any additional value that's been added with the tag. For example, businesses can tag their BCH coins with reward points that are redeemable for discounts. This is currently under development.