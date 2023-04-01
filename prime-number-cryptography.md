## Method 1 = clock

imagin a clock:\
? a clock 12 nums
```
a-> 7-1=6
b-> 13-1=12
c-> 6*12=72

encryption: y = x^5
decryption: x = y^29
```
? clock gears up!\
72=12??? in positition are the same!

this is the prime number encryption decryption

---

## Method 2 = secreties!
hash(a) generating by hash(b), and can decipher hash(b) by using revert function from hash(a)

#### problem
```
___________________
|hash(a) | hash(b)|
___________________
    ^         |
    |    ____________
    |<---| xor hash |
	 ____________

__________________________
hash(a) -> xor -> hash(b)
__________________________
```

#### solution (key = random prime number, two side accepted that)
```
___________________
|hash(a) | hash(b)|
___________________
    ^         |
    |     |+ key |
    |    ____________
    |<---| xor hash |
	 ____________

__________________________________
hash(a) -> xor -> - key -> hash(b)
__________________________________
```
hash(b) like private key, hash(a) like a message or public key

usecase: "ratchet message encryption"

for more informatio, using this in "diffie hellman". in messaging purposes on not-blockchain applications just remember to "sync" and "deleting" message from the device. (look like End2End encryption)

---

## Method 3 = zk-proof of whisper statement?
problem: how to accept "n"
```
____________________________________________________
n = random prime number, accept by two sides
alice = a	->	proof = g*(a|b) % n
bob = b		->	proof = g*(a|b) % n
____________________________________________________
```
answer: using "ratchet - hash(a)" solution and in/on hashed conversation
```
________________________________
| n1        | n3               |
________________________________
|       n4      |   n2         |
________________________________
```
this conversation/convensition not like [Schrödinger's cat](https://en.wikipedia.org/wiki/Schr%C3%B6dinger%27s_cat) , and answer is O(1)=1 try.
