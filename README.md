# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
~~~
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char text[100], key[10], cipher[100];
    int matrix[3][3], i, j, k, sum, n;

    printf("Enter Plain Text: ");
    scanf("%99s", text);

    printf("Enter 9-letter Key: ");
    scanf("%9s", key);

    n = strlen(text);

    for (i = 0; i < n; i++)
        text[i] = toupper(text[i]);

    for (i = 0; i < 9; i++)
        key[i] = toupper(key[i]);

    for (i = 0; i < 3; i++)
        for (j = 0; j < 3; j++)
            matrix[i][j] = key[i * 3 + j] - 'A';

    while (n % 3 != 0)
        text[n++] = 'X';

    text[n] = '\0';

    for (i = 0; i < n; i += 3)
    {
        for (j = 0; j < 3; j++)
        {
            sum = 0;

            for (k = 0; k < 3; k++)
                sum += matrix[j][k] * (text[i + k] - 'A');

            cipher[i + j] = (sum % 26) + 'A';
        }
    }

    cipher[n] = '\0';

    printf("Plain Text: %s\n", text);
    printf("Key: %s\n", key);
    printf("Encrypted Text: %s\n", cipher);
    printf("Cipher Text: %s\n", cipher);

    return 0;
}
~~~

## OUTPUT
<img width="432" height="287" alt="image" src="https://github.com/user-attachments/assets/f54448f3-8e7e-4c2c-827d-ca672167c59b" />


## RESULT
Thus, the Hill cipher encryption program was implemented successfully using C language.

