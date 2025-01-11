## ARIA

ARIA encryption algorithm for image encrypting.</br>
App for Secure delivery of gray images:</br>
Encryption, Decryption: Aria (OFB)</br>
Secret Key Delivery: Merkle-Hellman knapsack</br>
Signature: ECDSA</br>


********************************************
How does it work?
Preconditions:
1. Alice and Bob agree on Curve parameters (Curve, G, n)</br>
2. Bob must give alice his public key B </br>
-> Using Merkle-Hellman: Encrypt “Aria private key” with Bob’s public key B + Signing message using ECDSA</br>
<- Verify message using ECDSA + Using Merkle-Hellman: Decrypt “Aria private key” with Bob’s private key</br>
-> Using ARIA: Encrypt the photos using private key + Signing message using ECDSA</br>
<- Verify message using ECDSA + Using ARIA: Decrypt the message using  ARIA private key</br>

********************************************

If compiling with gcc, run:

```bash
gcc grayimage.c hash.c knapsack.c ECDSA.c ARIA.c -o program.exe
program.exe
```

<h3>Important !</h3>
In order for the project to work you need to create a solution or build the project.</br>
In the project the ARIA protocols as it was developed originally, using also knapsack algorithm</br>
and ECDSA in addition to a small hash function.</br>

was only a demonstration and I know it is not the best hash nor the best integers to use in the other algorithm.</br>
The project was to learning purpose and should not be used to encrypt important data.</br>