# generate private key, blind method 
how to generate private key for make public key and wallet address.\
example psuedo code:
```js
p = random()
q = random()
t = p * q

x = t % p
y = q % x

private_wallet = hash(y)
```

example output:
```js
p = 655061542424384900
q = 671120875099921200
t = 4.396254755961573e+35
x = 391863794422382340
y = 279257080677538800
// solidity -> bytes32 prvKey = keccak256(abi.encodePacked(y))

private key = 0x96ee4fda279de09402bddb98502e5638562fcc4cf5385935810c437fc2ce3f8c
public key = 0xb5a386eb2b58d1a66a1aad3beca6e139e87075d567dbfb67640a9c7e6abafbd99c9013a7b06d3a84bf1bb6aef1f9bed9c19824873029d953928fa8202d9bb03c
address = 0x9060e832a21c1b04dca33ebf8b827504bb0000fe
```

this private key work & generate the address on this code, but not add to your wallet.\
disclaimer: do not using this example private key on your product.
