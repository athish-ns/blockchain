# Simple Blockchain Implementation in Python

This repository contains a simple implementation of a blockchain in Python. The blockchain is a decentralized, distributed ledger technology that maintains a continuously growing list of records, called blocks, secured from tampering and revision. Each block contains a timestamp and a link to the previous block.

## Features

- **Blockchain Class**: Implements the core functionality of the blockchain, including block creation, transaction management, proof-of-work consensus, and conflict resolution.
- **Proof of Work**: Utilizes a simple proof-of-work algorithm to secure the blockchain against spam and abuse.
- **Node Registration and Consensus**: Enables adding new nodes to the network and resolving conflicts through consensus among nodes.

## Components

### 1. Blockchain Class

#### Initialization (`__init__`)

- Initializes the blockchain with an empty list of transactions and creates the genesis block.

#### Node Registration (`register_node`)

- Adds new nodes to the network to participate in consensus.

#### Validating the Chain (`valid_chain`)

- Checks the integrity of the blockchain by verifying the hashes and links between blocks.
- Validates proof of work and ensures consensus among nodes.

#### Consensus Algorithm (`resolve_conflicts`)

- Resolves conflicts among different nodes in the network by replacing the current chain with the longest valid chain.

#### Creating New Blocks (`new_block`)

- Creates a new block with a provided proof of work and the hash of the previous block.
- Includes a list of transactions and a timestamp.

#### Adding Transactions (`new_transaction`)

- Adds new transactions to the list of pending transactions.
- Represents exchanges of assets between participants in the network.

#### Retrieving the Last Block (`last_block`)

- Retrieves the last block in the blockchain.

#### Hashing Function (`hash`)

- Generates a SHA-256 hash of a block.
- Ensures the integrity and immutability of blocks.

#### Proof of Work (`proof_of_work`)

- Implements a simple proof-of-work algorithm to find a suitable proof for a new block.
- Requires finding a nonce (proof) that, when combined with the previous block's hash, produces a hash with specific criteria.

#### Validating Proof (`valid_proof`)

- Validates the proof of work by checking if the hash of the concatenated values of the previous proof, current proof, and previous block hash meets certain criteria.

### 2. Usage

1. **Initialization**: Create a new instance of the `Blockchain` class.
2. **Transaction**: Add new transactions using the `new_transaction` method.
3. **Mining**: Generate new blocks by running the proof-of-work algorithm with the `proof_of_work` method and then creating a new block with the `new_block` method.
4. **Consensus**: Resolve conflicts among different nodes in the network using the `resolve_conflicts` method.

### 3. Example

```python
blockchain = Blockchain()
blockchain.new_transaction(sender="sender_address", recipient="recipient_address", amount=5)
last_block = blockchain.last_block
proof = blockchain.proof_of_work(last_block)
previous_hash = blockchain.hash(last_block)
blockchain.new_block(proof, previous_hash)
print(blockchain.chain)
blockchain.resolve_conflicts()
```

This example demonstrates the creation of a new blockchain, addition of a transaction, mining of a new block, printing of the updated blockchain, and resolution of conflicts in the network.

## Conclusion

This repository provides a foundation for understanding and implementing blockchain technology in Python. Feel free to explore, experiment, and contribute to further enhancements and optimizations based on specific use cases and requirements.

