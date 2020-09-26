---
title: Merkle Trees!
layout: post
---

Merkle trees provide a time and space-efficient way of hashing nested values. Merkle tree nodes contain the
value of the hashes of its children, until the individual hashable leaf nodes. Modified versions are used in
blockchain networks like Bitcoin and Ethereum.

![A diagram depicting Merkle Tree hashing](https://decryptionary.com/wp-content/uploads/2017/12/merkle-tree-image.png)

As shown in the diagram, the hash of each parent is simply the hash of its children. If the node is a child, then it is simply its own hash. This results in a tree of hashes corresponding to each node in a tree.

Why is this useful? Algorithmically, Merkle trees allow for logarithmic search of changes, since every parent from the node will be different from its original state. Similarly, lookups of leaf nodes are also logarithmic (since the number of leaves is proportional to the log of the # of leaves).

Another use case is in many blockchains, where Merkle trees serve as a basis for validation of legitimate transfers, since the Merkle hash depends on the values of its children, and each blockchain transfer is essentially appending the root of the previous tree to a new node.

A simple, hacky, gist can be found [here](https://gist.github.com/ilknarf/e442135939bb9d56664d18f41a5ba03c)
