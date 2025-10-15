# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm
## NAME:VIMALA SAHANA W
## REG NO: 212223040241
## DATE:09-10-25
## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```
#include <stdio.h>
long long int mod_exp(long long int base, long long int exp, long long int mod) {
long long int result = 1;
while (exp > 0) {
if (exp % 2 == 1)
result = (result * base) % mod;
exp = exp >> 1; 
base = (base * base) % mod;
}
return result;
}
int main() {
long long int P, G, a, b, x, y, ka, kb;
printf("Enter the value of P: ");
scanf("%lld", &P);
printf("Enter the value of G (Primitive root of P): ");
scanf("%lld", &G);
printf("Enter the private key for VIMALA (a): ");
scanf("%lld", &a);
x = mod_exp(G, a, P);
printf("Enter the private key for SAHANA (b): ");
scanf("%lld", &b);
y = mod_exp(G, b, P);
ka = mod_exp(y, a, P); 
kb = mod_exp(x, b, P); 
printf("\nShared secret key for Alice : %lld\n", ka);
printf("Shared secret key for Bob : %lld\n", kb);
return 0;
}
```


## Output:
<img width="524" height="276" alt="image" src="https://github.com/user-attachments/assets/59fc80f1-24cd-429d-ac2b-bb6f07b9901e" />



## Result:
Thus the program was executed successfully.
  The program is executed successfully

