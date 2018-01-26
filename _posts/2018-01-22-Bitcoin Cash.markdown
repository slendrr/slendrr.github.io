---
layout: post
permalink: /bitcoincash
title:  "Bitcoin Cash"
date:   2018-01-22 00:00:00 +0000
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
Block confirmation: Proof-of-work<br>
Mining algorithm: SHA-256<br>
Block size: 8mb<br>
Developments: Graphene, Gigablock Testnet Initiative, Colored Coins

<h2>Summary</h2>
Bitcoin Cash is a hardfork of the original Bitcoin. When the community disagreed on how to scale Bitcoin and handle the growing number of transactions, they split into two groups. One group stayed with the 1mb block-size and maintained the Bitcoin name. Another group decided to increase the block-size to 8mb and adopt the name 'Bitcoin Cash'. Bitcoin Cash does not have replace-by-fee, SegWit, or the Lightning Network. All other elements of Bitcoin Cash remain the same as the original Bitcoin. This post will only focus on the differences.

<b>Hardforks</b> occur when the network cannot agree on the validity of the next block. This could be due to a disagreement between which transactions to include in the block or changes to the protocol itself. Although all validators start with the same block, validators can mine subsequent blocks that are incompatible with each other, forming separate chains and causing 'forks' in the blockchain. Hardforks can occur as often as there are disagreements between validators, but the legitimacy of a hardfork depends on the amount of network support it receives.

<h2>implications of Block-size Scaling</h2>

The block-size determines how many transactions can be included in a block. When a block is full, additional transactions will have to wait for the next block in order to be added to the blockchain. These are called unspent transactions and will collect in the network's memory pool. To circumvent this, users can pay higher transaction fees and incentivize miners to include their transactions first, thus earning more transaction fees from the block reward. As the unspent transactions memory pool grows, so do the confirmation times and transaction fees.

Increasing the block-size is the simplest and most straight-forward way to handle additional transactions, but it also causes concerns regarding storage space and bandwidth requirements of running a full node. As blocks get bigger and bigger to accommodate the growing number of transactions, the storage space required for saving a copy of the blockchain would grow at an increased rate. Larger block sizes also hold longer lists of transactions, which would take longer to propagate throughout the network, increase bandwidth, and reduce network efficiency.

<h2>current Developments</h2>

<b>Graphene</b> is a protocol for block propagation using set reconciliation. Normally, when network nodes receive transactions and build a block, they must propagate the list of transactions to the rest of the network to make sure the entire network is updated. Faster block propagation increases security and reduces the chance for slower nodes to waste processing power working on outdated blocks. Graphene accomplishes this by encoding the transactions list using a 'Bloom filter' to create an 'Invertible bloom lookup table (IBLT)'. Basically, the list of transactions is compressed into a much smaller, invertible data set. The key here is the word 'invertible', which means the compressed and filtered transaction list can be reversed. The filtered data is reduced to roughly 10% of the orignial size, allowing must faster propagation throughout the network. This improvement greatly reduces the bandwidth requirements of scaling Bitcoin Cash by increasing the block-size. The official whitepaper for Graphene can be found <a href="http://forensics.cs.umass.edu/graphene/graphene-short.pdf">here</a>.

<b>Gigablock Testnet Initiative</b> explores the possibility and implications of running the Bitcoin Cash network with 1GB blocks. The purpose of this project is to find out if a network of this scale is actually viable. If there are problems, then the researchers can brainstorm ideas in advance and begin developing solutions today. The goal is not to implement 1GB blocks immediately, rather it is just an exercise to further test big block scaling.

<b>Colored Coins</b> is a way for users on the Bitcoin Cash blockchain to issue their own coin on the network. Similar functionalities are already available in other cryptocurrencies, often referred to as digital tokens or digital assets. The idea is to 'color' some BCH that you own with a cryptographic tag. The BCH you've tagged can be spent as a regular BCH coin as well as any additional value that's been added with the tag. For example, businesses can tag their BCH coins with reward points that are redeemable for discounts. This is currently under development.