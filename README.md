# Cryptography

## What is Cryptography
* Definition: Converting some plain text into cipher text through mathematical equations
* Used for making sure that even if an attacker gets to information, it looks like gibberish without the decryption key
* Three main concepts in industry cryptography
  * Hashes
  * Symmetric cryptography
  * Asymmetric cryptography

## Ciphers
* A means of putting something into a secret code by means of an algorithm
* For example, a [Caesar cipher](https://cryptii.com/pipes/caesar-cipher), which is one of the first and most basic forms of cipher. It assigns each letter of the alphabet to a number, A=1 B=2 C=3 etc., and utilizes a set numerical key added to the number values of each letter.
* In industry you will not write your own encryption algorithms. You will use ones that have been written and thoroughly tested by researchers. This ensures it will be secure and statistically impossible to crack (ex. MD5, SHA 1)

## Hashes 
* Also known as digests or checksums
* A one-way mathamatical algorithm that takes data of arbitrary size and converts in to a bit string of fixed size
* If a file has the same exact information it will have the same hash, even if it is at a different location or posted somewhere else
* Works as a kind of tamper-evident seal for software. If something has been changed, the hash will be different. Because of this it's useful to check the checksum of things you download so you know that it hasn't been tampered with and is the same as what the developer published. [Example](https://www.kali.org/downloads/)
* FBI keeps hashes of illegal images so that, without storing those images in a database, they can identify illegal data by the hash instead of by the actual images

## Symmetric
![](CryptographyNotes/symmetric diagram.png)
* Uses one key to both encrypt and decrypt, thus both parties have to know the secret key in order to communicate
* You can just exchange this key with the person you want to communicate with
* Or you can use the Diffie-Hellman key exchange
	* pick 2 large primes g and p and send them to the person you want to exchange keys with
	* pick a secret number a, they will also pick a secret number b
	* compute g<sup>a</sup> mod p, we will call this A, they will do the same with their b and call it B
	* Exchange the numbers A and B
	* From there, you can compute B<sup>a</sup> mod p and A<sup>b</sup> mod p
	* Simplified: (g<sup>a</sup> mod p)<sup>b</sup> mod p = g<sup>ab</sup> mod p and (g<sup>b</sup> mod p)<sup>a</sup> mod p = g<sup>ba</sup> mod p

## Asymmetric
![](/asymmetric diagram.png)