# Information Security
> 7 types Algorithm Cryptography
> https://juejin.im/post/6844903638117122056
### use case 1
![](https://i.imgur.com/ZN94Z6j.png)
![](https://i.imgur.com/W07F5GL.png)


## RSA加密算法
> features
1.asymmetric 非对称means that it works on two different keys i.e Public key and private key

**Example1**
1.A clinet(for example brower) sends its public key to the server and requests for some data.
2.The server encrypts the data using client's public key and sents the encrypted data
3.Client decrypts it.

> **The idea**
> it is difficult to factorize a large integer(two large prime numbers mul两质数相乘得到的大数，反向推很难)
Public key(one,the other number is large integer)
Private key is also derived from the same prime numbers.
encryption strength totallly lies on the key size and if we double or triple the key size, the strength of encryption increases exponentially.**RSA 1024 or 2048 bits long**

**Example2**
```
* Select two prime no's. Suppose P = 53 and Q = 59.
Now First part of the Public key  : n = P*Q = 3127.

*  We also need a small exponent say e : 
But e Must be 

* An integer.

* Not be a factor of n.
 
* 1 < e < Φ(n) [Φ(n) is discussed below], 
Let us now consider it to be equal to 3.

    
* Our Public Key is made of n and e

---------------------------------------------
* We need to calculate Φ(n) :
Such that Φ(n) = (P-1)(Q-1)     
      so,  Φ(n) = 3016

    
* Now calculate Private Key, d : 
d = (k*Φ(n) + 1) / e for some integer k
For k = 2, value of d is 2011.


-------------------------------------------
* Convert letters to numbers : H  = 8 and I = 9

    
* Thus Encrypted Data c = 89e mod n. 
Thus our Encrypted Data comes out to be 1394


Now we will decrypt 1394 : 
    
* Decrypted Data = cd mod n. 
Thus our Encrypted Data comes out to be 89

8 = H and I = 9 i.e. "HI".

```



```
// C program for RSA asymmetric cryptographic 
// algorithm. For demonstration values are 
// relatively small compared to practical 
// application 
#include<stdio.h> 
#include<math.h> 

// Returns gcd of a and b 
int gcd(int a, int h) 
{ 
	int temp; 
	while (1) 
	{ 
		temp = a%h; 
		if (temp == 0) 
		return h; 
		a = h; 
		h = temp; 
	} 
} 

// Code to demonstrate RSA algorithm 
int main() 
{ 
	// Two random prime numbers 
	double p = 3; 
	double q = 7; 

	// First part of public key: 
	double n = p*q; 

	// Finding other part of public key. 
	// e stands for encrypt 
	double e = 2; 
	double phi = (p-1)*(q-1); 
	while (e < phi) 
	{ 
		// e must be co-prime to phi and 
		// smaller than phi. 
		if (gcd(e, phi)==1) 
			break; 
		else
			e++; 
	} 

	// Private key (d stands for decrypt) 
	// choosing d such that it satisfies 
	// d*e = 1 + k * totient 
	int k = 2; // A constant value 
	double d = (1 + (k*phi))/e; 

	// Message to be encrypted 
	double msg = 20; 

	printf("Message data = %lf", msg); 

	// Encryption c = (msg ^ e) % n 
	double c = pow(msg, e); 
	c = fmod(c, n); 
	printf("\nEncrypted data = %lf", c); 

	// Decryption m = (c ^ d) % n 
	double m = pow(c, d); 
	m = fmod(m, n); 
	printf("\nOriginal Message Sent = %lf", m); 

	return 0; 
} 
// This code is contributed by Akash Sharan. 

```

## SHA加密

