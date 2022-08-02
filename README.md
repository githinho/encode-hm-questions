# Encode homework answers

Answers to questions for Encode Expert Solidity July 2022.

For all resource see: [Encode notion page](https://encodeclub.notion.site/4-Practice-through-homework-and-exercises-488b446c267743d6a3aec2830fc38688).

## Homework 1

1. What information is held for an Ethereum account? Nonce, balance, code hash, storage root.
2. Where is the full Ethereum state held? In the World State Tree.
3. What is a replay attack? which 2 pieces of information can prevent it? Reply attack is when use signed and completed transaction and reuse, resend to network. It is prevented with nonce and chainId.
4. What checks are made on transactions for view functions? TODO:

## Homework 2

See repo: [https://github.com/githinho/encode-hm2](https://github.com/githinho/encode-hm2).

## Homework 3

1. What are the advantages and disadvantages of the 256 bit word length in the EVM? Advantage is optimal usage of keccak256 hash scheme and elliptic-curve computations. Disadvantage is nonoptimal storage for values below 256b like boolean, uint16.
2. What would happen if the implementation of a precompiled contract varied between Ethereum clients? Different clients would run different operations which would manifest in different outputs of the nodes/clients and the consensus could not be reached.
3. Do we need to validate the beneficiary field in the Ethereum block? No because it only states the address where should the reward and mining fees go.
4. Using Remix write a simple contract that uses a memory variable, then using the
debugger step through the function and inspect the memory.

## Homework 4

1. How can the use of tx.origin in a contract be exploited? By writing the contract which would call wanted contract and have tx.origin value the address of user which called our contract.
2. What do you understand by event spoofing? TODO:
3. What problems can you find in this [contract](https://gist.github.com/extropyCoder/a627d36d7ab5b1923db8145517051199) designed to produce a random number. The miner sets timestamp so he can always know the random number, it’s not random anymore.
4. What problems are there in this [contract](https://gist.github.com/extropyCoder/3a8a7f7a206041e38ee832cfa4abbd8e). You can call welcomeStundents() multiple times and get different startingNumber for the same number of students. Solution is to set `startingNumber=0;` at the start of the function `welcomeStudents()`.

## Homework 5

1. Look at the example of init code in today's notes. See [gist](https://gist.github.com/extropyCoder/4243c0f90e6a6e97006a31f5b9265b94). When we do the CODECOPY operation, what are we overwriting? 1. Overwriting the free memory pointer.
(debugging this in Remix might help here)
2. Could the answer to Q1 allow an optimisation? Yes, skip setting the free memory pointer at the start (first 3 commands and start from CALLVALUE).
3. Can you trigger a revert in the init code in Remix? Yes, by sending some ether.
4. Can you think of a situation where the opcode EXTCODECOPY is used? For setting contract owner.

## Homework 6

See repo: [https://github.com/githinho/encode-hm6](https://github.com/githinho/encode-hm6).
