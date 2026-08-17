# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```
#include <stdio.h>
#include <string.h>

void aesSim(char *in, char *key, char *out, int len)
{
    int keyLen = strlen(key);
    for(int i = 0; i < len; i++)
        out[i] = in[i] ^ key[i % keyLen];
    out[len] = '\0';
}

int main()
{
    char text[100], key[100], enc[100], dec[100];

    printf("Enter URL: ");
    fgets(text, sizeof(text), stdin);
    text[strcspn(text, "\n")] = '\0';

    printf("Enter Key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';

    int len = strlen(text);

    aesSim(text, key, enc, len);

    printf("Encrypted Data: ");
    for(int i = 0; i < len; i++)
        printf("%02X ", (unsigned char)enc[i]);

    printf("\n");

    aesSim(enc, key, dec, len);

    printf("Decrypted Data: %s\n", dec);

    return 0;
}
```

# OUTPUT:

<img width="1455" height="725" alt="image" src="https://github.com/user-attachments/assets/300a95aa-6701-48a7-a5f3-262ff7519919" />

# RESULT:

We have Successfully executed the program.
