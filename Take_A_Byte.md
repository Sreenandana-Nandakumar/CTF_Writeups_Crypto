# TAMUCTF2022
## Take a byte
### Challenge points: 500 
#### Description: We found this code along with these numbers. Any idea on what to do?
##### Challenge File
![Challenge file](./data.txt)
###### Solution:
On observing the text file given to us, we can see that the encrypted flag gigem{..} has been given to us along with the modulus and public exponent. 

In this challenge each character of the flag has been encrypted into a ciphertext which is split into a list.

The ascii readable range is between 0 and 256 within which the plaintext exists i.e. each ciphertext corresponds to an encrypted plaintext character.

Knowing that pt^e(modN) = ct
```py
new=[int(x) for x in s]         #s is all the ciphertexts taken as a string.
for ct in new:
	for char in range(250):
		if pow(char,e,N)==ct:
			print(chr(char),end="")
```

##### Flag: gigem{enumerable_SeArCh_SpAcEs_4R3_WEAK_xBEEF}
