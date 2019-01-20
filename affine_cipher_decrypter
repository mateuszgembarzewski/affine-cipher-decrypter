#include <iostream>
#include <sstream>

using namespace std;

// Naive implementation of modInverse
int modInverse(int a, int m)
{
    a = a%m;
    for (int x=1; x<m; x++)
       if ((a*x) % m == 1)
          return x;
    return -1;
}

// Determine the ordinal value of c
unsigned int ordinal(const char c) {
    return c - 97;
}

// Determine character representation of c
char character(const unsigned int c) {
    return (char) (c + 97);
}

string decrypt(const string ciphertext, int a, int b) {
   
   /* TODO: write code that decrypts ciphertext, given affine
    * parameters a and b.
    *
    * HINT: the % operator returns division after remainder; for
    * negative numbers, that is not the same as modulus. 
    */
	stringstream plaintext;
		for(int i = 0; i < ciphertext.length(); i++ ) 
		{
			//Decrypt cycle x = a'(y - b) % 26 
			//where y is the ciphertext char being decrypted
			
			int x = 0; // X represents the result of the decryption  
			int aPrime = modInverse(a,26);
			x = (aPrime * ( ordinal(ciphertext[i]) + (- b + 26)  )) % 26;
			plaintext << character(x);
			
		}
	return plaintext.str();

}

int main() {
    // TODO: your code goes here
	string ciphertxt = "edsgickxhuklzveqzvxwkzukcvuh";
	cout<<"The plaintext was: "<<decrypt(ciphertxt, 9 , 10)<<endl; 
	return 0;
}
