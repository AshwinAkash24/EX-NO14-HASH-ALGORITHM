# EX-NO14-HASH-ALGORITHM
## Submitted By:Ashwin Akash M
## Reference Number:212223230024
## AIM:
To implement HASH ALGORITHM

## ALGORITHM:

1. Prompt the user to enter a message (with spaces allowed).<br>
User Input – Understanding how programs receive data through the
console using scanf.
2. Read the entire message input until a newline.<br>
Handling Strings with Spaces – Using scanf("%[^\n]") to read
full lines, not just single words.
3. Compute a simple hash by combining XOR and addition of each
character.<br>
Hash Functions Basics – A lightweight technique to create a digital
fingerprint of data.
4. Display the computed hash in hexadecimal format.<br>
Hexadecimal Output – Representing binary data in a compact and
human-readable way using %02x.
5. Prompt and read the received hash value from the user (in hex).<br>
String to Integer Conversion – Converting user-entered hex strings
to numeric form with sscanf.
6. Compare the computed and received hash to verify message integrity.<br>
Data Integrity Check – Ensuring the message hasn’t been tampered
with by matching hashes.

## Program:
```
#include <stdio.h>
#include <string.h>
void computeSimpleHash(const char *message, unsigned char *hash)
{
 unsigned char temp = 0;
 for (int i = 0; message[i] != '\0'; i++)
 {
 temp = temp ^ message[i];
 temp += message[i];
 }
 *hash = temp;
}
int main()
{
 char message[256];
 unsigned char hash;
 char receivedHash[3];
 printf("Enter the message: ");
 scanf("%255[^\n]", message);
 computeSimpleHash(message, &hash);
printf("Computed Hash (in hex): %02x\n", hash);
 printf("Enter the received hash (in hex, 2 digits): ");
 scanf("%2s", receivedHash);
 unsigned int receivedHashValue;
 if (sscanf(receivedHash, "%x", &receivedHashValue) != 1)
 {
 printf("Invalid hash input.\n");
 return 1;
 }
 if (hash == receivedHashValue)
 {
 printf("Hash verification successful. Message is unchanged.\n");
 }
 else
 {
 printf("Hash verification failed. Message has been altered.\n");
 }
 return 0;
}
```

## Output:
![Screenshot 2025-04-19 135849](https://github.com/user-attachments/assets/e0330b3e-04c6-42c5-be43-ba80b679fc26)
![Screenshot 2025-04-19 135910](https://github.com/user-attachments/assets/839c4225-f24e-47b5-a432-45757f3cf1dc)

## Result:
The program is executed successfully.
