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

I followed the commands in the [Tips section](https://terokarvinen.com/trust-to-blockchain/#homework) and was able to create a wallet called `satus_default_wallet`:

![image](https://github.com/user-attachments/assets/17a44bba-bc68-4931-9150-617f91838e1c)

## b. Faucet

In order to receive the money, I created a receive request in Electrum Testnet and copied the address:

![image](https://github.com/user-attachments/assets/a4bcd995-030d-4957-bac2-21dbb9e32dc2)

Then I went to the [Testnet faucet](https://coinfaucet.eu/en/btc-testnet/) website and pasted the address there. I got a confirmation that the bitcoin was transferred:

![image](https://github.com/user-attachments/assets/e6e14377-24ed-4616-a6ad-b02c11045b2d)

And indeed, I saw some bitcoins in my wallet:

![image](https://github.com/user-attachments/assets/b9c3a524-78c4-4a3a-8ab2-60329bb5118a)
![image](https://github.com/user-attachments/assets/8b7d19ff-276a-4a4f-9031-2eba7101ae9a)

## c. Giveaway

I decided to give some bitcoins to my other wallet as I was not sure how I could send it to someone else. Creating another wallet called `wallet_1` was very easy but when sending the bitcoins, I got a lot of issues. The system was warning about the fees and even after raising the fees, the transaction ended up in error, saying that the fees were too low. Finally I was able to create a local transaction, which was visible in the both wallets' histories and the amount of bitcoins got updated too.

Bitcoins left from `satus_default_wallet`:

![image](https://github.com/user-attachments/assets/65de34c2-5d3b-4d66-a865-9d2d2894f718)

The transaction:

![image](https://github.com/user-attachments/assets/f8041aa3-8f12-4098-a5b5-a4d028d0a6d3)

Bitcoins arrived to the `wallet_1`:

![image](https://github.com/user-attachments/assets/15c3657b-fd97-495e-927f-48975823a62e)

## d. Recycle

First I copied the Testnet address from the same website I got the bitcoins originally from:

![image](https://github.com/user-attachments/assets/7d1d9d54-825c-4e81-ae65-c24a98a94550)

I pasted the address in Electrum, and tried to send some of my bitcoins. Finally succeeded but as you can see from the "Send queue", I had tried already quite many times. Finally changing the network (from Tools), made it possible to send..:
![image](https://github.com/user-attachments/assets/a2873ffd-f5f2-473e-9ae6-109d8f5e5d3d)

History, bitcoins left:

![image](https://github.com/user-attachments/assets/2a25bafb-c463-44b6-a1ff-4d6699266bb5)

Now when it finally worked, I decided to send the rest of my bitcoins and my wallet is empty:
![image](https://github.com/user-attachments/assets/1ea843b2-2ac0-4141-8d19-bf4deb5edd98)

## e. Explorer

I tried to find some interesting bitcoin blocks, but at least ChatGPT could not help me, all its example transactions could not be found from the explorers (I tried blockchair, blockchain and bitaps sites). So I gave up and explored one basic example..:

I used [blockchain.com](https://www.blockchain.com/explorer) and chosed one random block [id #870884](https://www.blockchain.com/explorer/blocks/btc/870884), and random transaction [hash e07bc8c0e06d27b1097b059fb5b536c11a30af9dba4d874be322b98037ce702a](https://www.blockchain.com/explorer/transactions/btc/e07bc8c0e06d27b1097b059fb5b536c11a30af9dba4d874be322b98037ce702a)

I found Blockchain very clear tool and it also gave descriptions on all the fields so I was able to understand the information better.

**Block information**

| Field         | Description                                                     | Value                                                            |
| ------------- | --------------------------------------------------------------- | ---------------------------------------------------------------- |
| Hash          | Unique identifier to the block                                  | 0000000000000000000138c3e0803889c50a59d34d94ef9ab16002ec35ddd864 |
| Distance      | Time since the block was mined                                  | 1h 25m 0s                                                        |
| BTC           | Bitcoins sent on all transactions of the block                  | 1,549.3715                                                       |
| Value         | Value of all transactions when the block was mined              | 143,195,873 $                                                    |
| Value today   | Present value                                                   | 142,115,232 $                                                    |
| Average Value | Average value of a transaction                                  | 0.3172341314 BTC                                                 |
| Input Value   | All transactional input values summed together                  | 1,549.42 BTC                                                     |
| Output Value  | All transactional output values summed together                 | 1,552.54 BTC                                                     |
| Transactions  | Amount of transactions in the block                             | 4,884                                                            |
| Fees          | Transaction fees rewarded to the miner for calculating the hash | 0.04673086 BTC                                                   |
| Average fee   | Average fee amount/transaction on the block                     | 0.00000957                                                       |
| Depth         | How deep in the confirmed blocks                                | 1                                                                |
| Size          | Total size of the bloc                                          | 1,539,788                                                        |
| Nonce         | Random value that can be adjusted to satisfy the Proof-Of-Work  | 1,965,728,596                                                    |
| Height        | Number of blocks connected on the blockchain                    | 870,884                                                          |
| Miner         | Who confirmed block's transactions                              | AntPool                                                          |

**Sample transaction**

| Field   | Description                                     | Value                                                            |
| ------- | ----------------------------------------------- | ---------------------------------------------------------------- |
| Hash ID | Unique identifier to the transaction            | e07bc8c0e06d27b1097b059fb5b536c11a30af9dba4d874be322b98037ce702a |
| Amount  | How many bitcoins got transferred               | 0.01917652 BTC, 1,753.35 $                                       |
| Fee     | Total fees paid to process transaction          | 0.00144170 BTC                                                   |
| From    | How many inputs                                 | 15 inputs                                                        |
| To      | How many outputs                                | 2 inputs                                                         |
| Time    | When transaction was broadcasted to the network | 18 Nov 2024 05:57:13                                             |

Here's more information about the inputs and outputs as it was a bit unclear to me:

- UTXO = Unsppent transaction output
- Each input includes a reference to previous UTXO combined with a cryptographic digital signature
- Digital signature is generated using the sender’s private key. It is a proof that the sender has the right to spend the bitcoin
- Output defines where the bitcoin is going, including the amount of bitcoin to be transferred and rules how the receiver can spend them

Reference: Theedtron, 2024. Bitcoin transactions for dummies. URL: https://medium.com/@theedtron/bitcoin-transactions-for-dummies-fd85e17c31b9. Accessed: 18 November 2024.

## f. RogeCoin

**1. Investing in chryptocurrency is the same as gambling (0:52)**

Support:

- To my experience, the future of cryptocurrency is very hard to predict and it's very hard to say if you will win or lose, just like in gambling

Challenge:

- Gambling is based on a chance, while cryptocurrency is based on cryptography
- Gambler is playing against the casino house, investor in cryptocurrency is playing against other people that has approx the same amout of money

**2. You will lose your cryptos if you forget your wallet password (2:53)**

Support:

- If you don't have any crucial information about the wallet, then indeed the cryptos will be lost. But this is nothing new. For example, to my understanding, there is no way to log in to password manager service if you lose your master password.

Challenge:

- There still are multiple ways to recover the passoword if you have some necessary information like encrypted wallet backup file or a device that has the wallet app installed (KeyChainX, 2024)
- I have invested in Bitcoin via Coinmotion service and there I don't need to remember any password, just login with bank acccount

**3. Like all good currencies, cryptocurrencies should be hoarded forever (3:43)**

Support:

- Some Bitcoin investors believe that the cryptocurrency will increase the value over the long term because its supply is fixed. The supply of Bitcoin is fewer than 21 million coins, on the other hand, most other currencies can be printed if central bankers decide so (Bylund, 2023)

Challenge:

- Just to check the past rates of Bitcoin, or any investment product, they will have ups and downs. Instead of keeping the cryptos forever, I think it's wise to keep an eye on rates and plan the correct timing of selling or buying more
- To my mind there is no investment that should kept forever :D

References:
KeyChainX 2024. How to recover lost Bitcoin wallet Password? URL: https://keychainx.medium.com/how-to-recover-lost-bitcoin-passwords-c34c42ee6f17. Accessed: 18 November 2024.
Bylund 2023. Is Cryptocurrency a Good Investment? URL: https://www.fool.com/investing/stock-market/market-sectors/financials/cryptocurrency-stocks/is-cryptocurrency-good-investment/. Accessed: 18 November 2024.
