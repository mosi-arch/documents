Zero Knowledge Proof (ZKP) is an encryption scheme that allows for proving the authenticity of a statement without revealing any additional information beyond what is necessary for the proof. [1] Here's a simple example of a ZKP algorithm in pseudocode:

```js
// Prover wants to prove knowledge of a secret value x in a range [1, N]
// Verifier wants to verify the proof without learning anything about x

// Prover:
x = random value in [1, N]
r = random value
h = hash(x, r) // hash function
y = x + r

// Send (h, y) to verifier

// Verifier:
h, y = receive from prover
assert y > 0 and y <= N + h_max // h_max is the maximum value of h that is allowed
assert hash(x, y - x) == h // check that (h, y) is a valid proof for x

// Done!
```

This is a simple example of a ZKP algorithm called a "discrete logarithm proof" that proves knowledge of a secret value x in a range [1, N] without revealing x. The idea is that the prover selects a random value r, computes y = x + r, and sends the verifier the hash of x and r (h) and y. The verifier checks that y is in the range [1, N + h_max] and that the hash of x and y - x equals h, which proves that the prover knows x without revealing it. There are many other types of ZKP algorithms with different properties and use cases, but they all rely on similar principles. [1]

References:\
[1] [Zero Knowledge Proof](https://www.geeksforgeeks.org/zero-knowledge-proof/)\
[2] [Code Talks: The A-to-Z on zkSnarks and Zero-Knowledge …](https://medium.com/@ppio/zksnarks-zero-knowledge-proof-feb76bf49e1a)\
[3] [Example of A Good Zero Knowledge Proof](https://101blockchains.com/zero-knowledge-proof-example/)
