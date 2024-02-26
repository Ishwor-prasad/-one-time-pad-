# -one-time-pad-
insecurity when a “one-time
pad” is reused. In this problem, all characters are represented as 8-bit bytes with the
ASCII encoding. Let M = (m1
, m2
, . . . , mn ) be a message, consisting of a sequence

of n message bytes, to be encrypted. Let P = (p1
, p2
, . . . , pn ) denote a pad,
consisting of a corresponding sequence of (randomly chosen) “pad bytes” (key
bytes). In the usual one-time pad, the sequence C = (c1
, c2
, . . . , cn ) of ciphertext
bytes is obtained by xor-ing each message byte with the corresponding pad byte:

ci = mi⊕ pi , for i = 1 . . . n .

1.
Consider the following two 8-character English words encrypted with the same
“one-time pad”. What are the words?

e9 3a e9 c5 fc 73 55 d5
f4 3a fe c7 e1 68 4a df

Hint: Use /usr/share/dict/words in Ubuntu OS as a representation of dictionary for
English words.

2.

Assume, one of your fellow students tries to fix this problem by making sure that you
can’t just cancel the pad bytes by xor-ing the ciphertext bytes. In her/his scheme the
key is still as long as the ciphertext. Suppose c0 = 0, then the ciphertext bytes c1
, c2
, .

. . , cn are obtained as follows:

ci = mi⊕ ((p i + ci−1 ) mod 256) .

That is, each ciphertext byte is added to the next key byte and the addition result
(modulo 256) is used to encrypt to the next plaintext byte. The student is now
confident s/he can reuse her/his pad, since (pi + ci−1 ) mod 256 will be different for
different messages, so nobody would be able to cancel the pi
’s out.

(1) Write a program that implements the new encryption and decryption scheme.
Show the result with a 10 character message and key.

(2) You are provided with a text file containing ten ciphertexts C1
, C2
, . . . , C10
produced by the new modified encryption and decryption technique. All of the
ciphertexts are generated using the same pad P. The messages contain valid
English text. Find the messages and the pad.

Hint:
1. The valid character set (characters of the plaintext) contains lowercase a – z,
uppercase A – Z, space , , . ? ! - ( ). Total number of characters is 60.

2. Try to figure out possible pads for the valid characters.

3. Try to find the words of the messages using the dictionary mentioned in problem
set 1.
