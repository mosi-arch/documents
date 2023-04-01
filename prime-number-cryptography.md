## method 1 = clock

imagin a clock:\
? a clock 12 nums
```
a-> 7-1=6
b-> 13-1=12
c-> 6*12=72

encryption: y = x^5
decryption: x = y^29
```
? clock gears up!

this is the prime number encryption decryption

---

## method 2 = secreties!

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
