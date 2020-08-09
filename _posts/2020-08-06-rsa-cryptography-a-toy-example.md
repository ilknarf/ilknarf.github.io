---
published: true
title: "RSA cryptography: a toy example"
layout: post
---

When RSA was introduced in 1977 it made breakthroughs in network communication, and is still used prevalently today in a variety of use cases. (In fact, according to [Wikipedia](https://en.wikipedia.org/wiki/RSA_(cryptosystem)), an equivalent cryptosystem was developed by the British Government by 1973! However, it was put on the backburner due to computational limitations at the time.)

RSA was novel in that fact that keys didn't need to be privately transmitted across networks to encrypt
and decrypt data; rather, a public key could be repeatedly used to encrypt data, while a private key would
be required to decrypt it, meaning that an agent would be able to encrypt messages without being able to
decrypt other messages using the same public/private keypair. This is the most common example of 
[public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography), where public keys can be 
transmitted across an unsafe network in order to encrypt, without risk of a malicious actor intercepting 
the key and decrypting messages.
```
# Given p1, p2 as large primes
semiprime = p1 * p2
totient(semiprime) = (p1 - 1) * (p2 - 1)
```
The system itself is based off the idea that factoring is way harder computationally than multiplying. It
uses a proven mathematical system that involves utilizing the triviality of computing totient functions of
primes (e.g. 7 is coprime with 6 numbers below it) and the multiplicativity of [totient functions]
(https://en.wikipedia.org/wiki/Euler%27s_totient_function) (the totient of 21 is the same as the totient
of 7 multiplied by the totient of 3) in order to construct a problem that is easy to solve when the primes 
are known, but computationally unfeasible without the primes) to create a one-way function to calculate 
private keys from arbitrary public keys.
```
# Given pub, priv keys of the p1, p2 system
5 ** (pub * priv) % semiprime == 5  # iff 5 ** (pub * priv) > semiprime
```

Given two large (secret) primes, the private key itself is the [modular inverse](https://en.wikipedia.org/wiki/Modular_multiplicative_inverse) of the arbitrary public key modulo the totient of the semiprime product of the two primes. Interestingly, this value pair can be used to exponentiate values modulo the semiprime to produce the initial value. However, calculating the private key from just the public key is near-impossible, making the public key safe to transmit. This is the basis for the RSA system, where the multiplication of numbers is relatively easy, while the factoring of the semiprime is very difficult. (As computers have become more powerful, using RSA requires larger and larger primes, as many not-large-enough primes can be feasibly factored).

![RSA Network Transmission Example Diagram](https://richardgoyette.com/Infosec/Alice/images/encrypt3.jpg)

In my [example code](https://gist.github.com/ilknarf/c596f86110d081385e49f171f748ca83), I've created a toy RSA system where encrypting produces string of space-separated hexadecimal digits. This isn't padded (which is a requirement for modern RSA systems, and I will likely touch upon on a future post), nor is it efficient, as I do not apply the square-then-modulus algorithm, which makes the calculations quicker.
