# VIGENERE-CIPHER
## EX. NO: 4
 

## IMPLEMETATION OF VIGENERE CIPHER
 

## AIM:

To implement the Vigenere Cipher substitution technique using C program.

## DESCRIPTION:

To encrypt, a table of alphabets can be used, termed a tabula recta, Vigenère square,or Vigenère table. It consists of the alphabet written out 26 times in differnt rows, each
 
alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses adifferent alphabet from one of the rows. The alphabet used at each point repeating keyword.depends on a Each row starts with a key letter. The remainder of the row holds the letters A to Z. Although there are 26 key rows shown, you will only use as many keys as there are unique letters in the key string, here just 5 keys, {L, E, M, O, N}. For successive letters of the message, we are going to take successive letters of the key string, and encipher each message letter using its corresponding key row. Choose the next letter of the key, go along that row to find the column heading that	atches the message character; the letter at the intersection of
[key-row, msg-col] is the enciphered letter.


## ALGORITHM:

STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.

STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.

STEP-3: Repeat this process for all 26 rows and construct the final key matrix.

STEP-4: The keyword and the plain text is read from the user.

STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.

STEP-6: Pick the first letter of the plain text and that of the keyword as the row indices and column indices respectively.

STEP-7: The junction character where these two meet forms the cipher character.

STEP-8: Repeat the above steps to generate the entire cipher text.


## PROGRAM:
def vigenere_encrypt(plain_text, key):
    plain_text = plain_text.upper()
    key = key.upper()
    cipher_text = ""

    for i in range(len(plain_text)):
        k = key[i % len(key)]
        encrypted_char = chr((ord(plain_text[i]) - 65 + ord(k) - 65) % 26 + 65)
        cipher_text += encrypted_char

    return cipher_text

def vigenere_decrypt(cipher_text, key):
    cipher_text = cipher_text.upper()
    key = key.upper()
    plain_text = ""

    for i in range(len(cipher_text)):
        k = key[i % len(key)]
        decrypted_char = chr((ord(cipher_text[i]) - ord(k) + 26) % 26 + 65)
        plain_text += decrypted_char

    return plain_text

# --- Menu Loop ---
while True:
    print("\n1. Encrypt Text\t2. Decrypt Text\t3. Exit")
    choice = input("Enter Your Choice: ")

    if choice == '3':
        break
    elif choice == '1':
        plain = input("Enter Plain Text: ").replace(" ", "").upper()
        key = input("Enter Key: ").replace(" ", "").upper()
        result = vigenere_encrypt(plain, key)
        print("Encrypted Text:", result)
    elif choice == '2':
        cipher = input("Enter Cipher Text: ").replace(" ", "").upper()
        key = input("Enter Key: ").replace(" ", "").upper()
        result = vigenere_decrypt(cipher, key)
        print("Decrypted Text:", result)
    else:
        print("Please Enter a Valid Option.")


## OUTPUT:
![image](https://github.com/user-attachments/assets/a8aa443d-5422-4b10-bbc2-bbd946e05754)


## RESULT:
The program is executed successfully
