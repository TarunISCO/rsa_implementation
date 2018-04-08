# RSA Implementation

RSA algorithm is asymmetric cryptography algorithm. The idea of RSA is based on the fact that it is difficult to factorize a large integer. The public key consists of two numbers where one number is multiplication of two large prime numbers. And private key is also derived from the same two prime numbers. So if somebody can factorize the large number, the private key is compromised. Therefore encryption strength totally lies on the key size and if we double or triple the key size, the strength of encryption increases exponentially. RSA keys can be typically 1024 or 2048 bits long, but experts believe that 1024 bit keys could be broken in the near future. But till now it seems to be an infeasible task.

## Mechanism behind RSA algorithm

### Generating Public Key
```
* Select two prime no's. Suppose P = 53 and Q = 59.
  Now First part of the Public key  : n = P*Q = 3127.
  
* We also need a small exponent say e : 
  But e Must be 
  * An integer.
  * Not be a factor of n.
  * 1 < e < Φ(n) [Φ(n) is discussed below], 
  
    Let us now consider it to be equal to 3.
    
* Our Public Key is made of n and e.
```

### Generating Private Key
```
* We need to calculate Φ(n) :
  Such that Φ(n) = (P-1)(Q-1) 
      so,  Φ(n) = 3016
      
* Now calculate Private Key, d : 
  d = (k*Φ(n) + 1) / e for some integer k
  For k = 2, value of d is 2011.
```

Now we are ready with our – Public Key ( n = 3127 and e = 3) and Private Key(d = 2011)

Now we will encrypt “HI” :

```
Convert letters to numbers : H  = 8 and I = 9

    
Thus Encrypted Data c = 89^e mod n. 
Thus our Encrypted Data comes out to be 1394


Now we will decrypt 1349 : 
    
Decrypted Data = c^d mod n. 
Thus our Encrypted Data comes out to be 89

8 = H and I = 9 i.e. "HI".
```
