# Problem Description

We found a brand new type of encryption, can you break the secret code? (Wrap with picoCTF{}) mlnklfnknljflfmhjimkmhjhmljhjomhmmjkjpmmjmjkjpjojgjmjpjojojnjojmmkmlmijimhjmmj 
[new_caesar.py](./new_caesar.py)

# Understanding the problem

![image](https://user-images.githubusercontent.com/123538724/220552760-7be8b964-a46a-4f8d-8a0e-04382c56a974.png)
The assert statements show that the key needs to be one character and be a letter between a to p.

![image](https://user-images.githubusercontent.com/123538724/220553251-e518e895-5f33-431c-aefe-07d40c55fc1e.png)
This piece of code outputs ASCII value of c in binary form  
Then breaks the binary number in two  
Then that integer is used as index of list ALPHABET and the letter at that index is added to the encryption  

![image](https://user-images.githubusercontent.com/123538724/220554258-60890424-4ea9-419a-b67f-e0175e2c127a.png)
The function shift returns a value in ALPHABET at the index ascii value of the c minus 97 plus the ascii value of the key minus 97 mod 16.

# Decryption

from itertools import *
import string

ALPHABET = string.ascii_lowercase[:16]
LOWERCASE_OFFSET = ord("a")
ALPHABET = string.ascii_lowercase[:16]

def b16_encode(plain):
	enc = ""
	for c in plain:
		binary = "{0:08b}".format(ord(c))
		enc += ALPHABET[int(binary[:4], 2)]
		enc += ALPHABET[int(binary[4:], 2)]
	return enc

def shift(c, k):
	t1 = ord(c) - LOWERCASE_OFFSET
	t2 = ord(k) - LOWERCASE_OFFSET
	return ALPHABET[(t1 + t2) % len(ALPHABET)]

def b16_decode(enc):
    dec = ""
    for i in range(0, len(enc), 2):
        binary = "{0:04b}".format(ALPHABET.index(enc[i])) + "{0:04b}".format(ALPHABET.index(enc[i+1]))
        dec += chr(int(binary, 2))
    return dec

enc = "kjlijdliljhdjdhfkfkhhjkkhhkihlhnhghekfhmhjhkhfhekfkkkjkghghjhlhghmhhhfkikfkfhm"
for key in ALPHABET:
    flag = ""
    print("Key:", key)
    for c in enc:
        flag += shift(c, key)
    print("Flag: ", b16_decode(flag))
        
Took help of a yotube video to write the reverse

# FLAG
picoCTF{et_tu?_1ac5f3d7920a85610afeb2572831daa8}

