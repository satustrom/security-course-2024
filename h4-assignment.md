# H4 assignment

## X. Summaries

#### **[Nakamoto 2008: Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf):**

**1. Introduction**

- Internet commerce relies heavily on financial institutions as trusted intermediaries for processing payments, but it also has inherent weaknesses, such as inability to create non-reversible transactions and increased transaction costs due to mediation

**2. Transactions**

- An electronic coin = a chain of digital signatures
- "mint" = a trusted central authority, much like a traditional bank
- Mint is needed to be used to check each transaction to verify that the coin hasn't been double-spent
- To prevent double-spending without a mint, transactions must be publicly announced and a system is needed for participants to agree on the chronological order of transactions (if there are multiple spent, the first one is the valid one)

**3. Timestamp Server**

- Timestamp server = hash of a block of data and publicly publishes the hash (like in a newspaper). This proves the data existed at the specified time.
- Each timestamp includes the previous timestamp in its hash, making a chain.

**4. Proof-of-Work**

- To implement a distributed timestamp server, the system uses a Proof-Of-Work mechanism, where participants must find a value (nonce) that when hashed, creates a hash with a specific number of leading zero bits
- Once a block satisfies the proof-of-work requirement, it becomes computationally impractical to alter. To change any block, an attacker would need to redo the proof-of-work for that block and all the other blocks in the chain, ensuring the integrity of the entire network.
- Proof-Of-Work solves the issue of determining consensus by using a "one-CPU-one-vote" system, rather than a "one-IP-one-vote" approach, which could be subverted by anyone with many IP addresses. The longest chain, with the most proof-of-work, represents the majority decision

**5. Network**

- Steps to run the network
  1. Broadcasting new transactions to all nodes
  2. New transactions collected into a block (by each node)
  3. Trying to find a difficult proof-of-work for its block (by each node)
  4. When a proof-of-work found, block broadcasted to all nodes (by the node that found it)
  5. Block accepted (by each node) only if all the transactions are valid and not already spent
  6. Use hash of the accepted block as the previous hash to trying to create the next block in the chain
- The longest chain is considered to be the correct one
- All the new transaction broadcasts don't need to reach all nodes, just if they reach many nodes, they will eventually get into a block

**6. Incentive**

- The first transaction in each block rewards the block creator with new coins, encouraging nodes to support the network and distribute coins without a central authority
- Although gold miners (=possible block creators) need to spend CPU time and electricity
- Fees from transactions can complement or eventually replace the block reward, ensuring a transition to a fee-based system once a set number of coins are minted.
- The block reward and fees encourage honest behavior, as attackers are more likely to generate new coins honestly than to undermine the system and risk their own wealth.

Reference: Nakamoto 2008. Bitcoin: A Peer-to-Peer Electronic Cash System. URL: https://bitcoin.org/bitcoin.pdf. Accessed: 17 November 2024.

## a. Wallet
I followed the commands in the Tips sections and was able to create a wallet 

![image](https://github.com/user-attachments/assets/17a44bba-bc68-4931-9150-617f91838e1c)



## b. Faucet

I was able to get money 
![image](https://github.com/user-attachments/assets/e6e14377-24ed-4616-a6ad-b02c11045b2d)

In order to receive the money, I created a receive request and copied the link to the testnet faucet website. See in the bottom that there are money received

![image](https://github.com/user-attachments/assets/a4bcd995-030d-4957-bac2-21dbb9e32dc2)


![image](https://github.com/user-attachments/assets/b9c3a524-78c4-4a3a-8ab2-60329bb5118a)
![image](https://github.com/user-attachments/assets/8b7d19ff-276a-4a4f-9031-2eba7101ae9a)


## c. Giveaway
Created a request
![image](https://github.com/user-attachments/assets/a838aac0-e228-4b94-9a81-561b308d0781)
![image](https://github.com/user-attachments/assets/65de34c2-5d3b-4d66-a865-9d2d2894f718)
![image](https://github.com/user-attachments/assets/f8041aa3-8f12-4098-a5b5-a4d028d0a6d3)

Lahetetty
![image](https://github.com/user-attachments/assets/7b306fa0-1e6d-4ad8-9280-402180c98d64)

Vastaanotettu toiselle lompakolle
![image](https://github.com/user-attachments/assets/15c3657b-fd97-495e-927f-48975823a62e)

## d. Recycle

![image](https://github.com/user-attachments/assets/7d1d9d54-825c-4e81-ae65-c24a98a94550)

I copied the link in the testnet site to send the money back
![image](https://github.com/user-attachments/assets/a2873ffd-f5f2-473e-9ae6-109d8f5e5d3d)

![image](https://github.com/user-attachments/assets/2a25bafb-c463-44b6-a1ff-4d6699266bb5)

Send also the rest back..
![image](https://github.com/user-attachments/assets/1ea843b2-2ac0-4141-8d19-bf4deb5edd98)


## e. Explorer

## f. RogeCoin
