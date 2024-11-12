# Ex-4 Vigenere Cipher

### DATE:

Vigenere Cipher using with different key values

## AIM:
To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:

Step 1: Design of Vigenere Cipher algorithnm

Step 2: Implementation using C or pyhton code

Step 3: Testing algorithm with different key values. ALGORITHM DESCRIPTION: The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.

## PROGRAM:
```
#include <iostream>
#include <cstring>
using namespace std;

// Function to perform Vigenère encryption
void vigenereEncrypt(char text[], const char key[]) {
    int textLen = strlen(text);
    int keyLen = strlen(key);

    for (int i = 0; i < textLen; i++) {
        char c = text[i];

        if (c >= 'A' && c <= 'Z') {  // Encrypt uppercase letters
            text[i] = ((c - 'A' + key[i % keyLen] - 'A') % 26) + 'A';
        } else if (c >= 'a' && c <= 'z') {  // Encrypt lowercase letters
            text[i] = ((c - 'a' + key[i % keyLen] - 'A') % 26) + 'a';
        }
    }
}

// Function to perform Vigenère decryption
void vigenereDecrypt(char text[], const char key[]) {
    int textLen = strlen(text);
    int keyLen = strlen(key);

    for (int i = 0; i < textLen; i++) {
        char c = text[i];

        if (c >= 'A' && c <= 'Z') {  // Decrypt uppercase letters
            text[i] = ((c - 'A' - (key[i % keyLen] - 'A') + 26) % 26) + 'A';
        } else if (c >= 'a' && c <= 'z') {  // Decrypt lowercase letters
            text[i] = ((c - 'a' - (key[i % keyLen] - 'A') + 26) % 26) + 'a';
        }
    }
}

int main() {
    const char *key = "KEY";  // Replace with your desired key
    char message[] = "SecurityLaboratory";  // Replace with your message

    // Convert message to uppercase for simplicity
    for (int i = 0; i < strlen(message); i++) {
        message[i] = toupper(message[i]);
    }

    cout << "Simulating Vigenère Cipher" << endl;
    cout << "Input Message: " << message << endl;

    // Encrypt the message
    vigenereEncrypt(message, key);
    cout << "Encrypted Message: " << message << endl;

    // Decrypt the message back to the original
    vigenereDecrypt(message, key);
    cout << "Decrypted Message: " << message << endl;

    return 0;
}
```
## OUTPUT:

![image](https://github.com/user-attachments/assets/58c0115c-3d01-4782-b0e7-be076a1febf5)

## RESULT:

The program is executed successfully.
