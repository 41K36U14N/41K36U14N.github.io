---

title:  "Caeser Cipher"
date: 2024-07-07 00:00:00 +0800 
categories: [Projects] 
tags: [projects, cipher] 
---
![Caeser Cipher header](/assets/Caesar-Cipher.png)

The Caesar Cipher is one of the simplest and most widely known encryption techniques. Named after Julius Caesar, who reportedly used it to communicate with his officials, this cipher is a type of substitution cipher where each letter in the plaintext is shifted a certain number of places down or up the alphabet. In this blog post, we'll explore what the Caesar Cipher is, how it works, and how you can implement it in Python.

![Julius Caeser](/assets/julius-caesar.webp)

### What is the Caesar Cipher?

The Caesar Cipher is a substitution cipher that shifts the letters in the plaintext by a fixed number of positions down the alphabet. For example, with a shift of 1, `A` would be replaced by `B`, `B` would become `C`, and so on, wrapping around to `A` after `Z`. This method is simple to understand and implement but is also easy to break with modern computational power.

### How Does It Work?

1. **Choose a Shift Key**: Decide how many positions each letter in the plaintext will be shifted. This number is the key for both encryption and decryption.
2. **Encrypting the Message**:
   - For each letter in the plaintext:
     - Find its position in the alphabet (0 for `A`, 1 for `B`, etc.).
     - Add the shift key to this position.
     - Wrap around if necessary (using modulo 26 for the alphabet).
     - Replace the original letter with the new letter at the shifted position.
3. **Decrypting the Message**: The decryption process is the reverse of encryption:
   - Subtract the shift key from the position of each letter in the ciphertext.
   - Wrap around if necessary.
   - Replace the ciphertext letter with the new letter at the shifted position.

- example 
```
plain text : You are the best
cipher txt : csy evi xli fiwx 
if shifted 4 characters to right 
```

![caeser wheel](/assets/caesar-cipher-wheel-.webp)

### Implementation in Python

To implement the Caesar Cipher in Python, we'll write functions to both encrypt and decrypt messages. The following steps will guide us through the implementation:

#### Step-by-Step Explanation

1. **Define the Alphabet**: Use a string containing all the letters of the alphabet for reference.
2. **Encrypt Function**:
   - Iterate over each character in the plaintext.
   - For each character, find its position in the alphabet.
   - Shift this position by the key.
   - Replace the character with the new character at the shifted position.
   - Handle both uppercase and lowercase letters, leaving non-alphabetic characters unchanged.
3. **Decrypt Function**: Reverse the encryption process by subtracting the shift key.
4. **Main Function**: Allow users to input the plaintext, key, and choose whether to encrypt or decrypt.

#### Code 1 

```python
def encrypt_caesar(plaintext, shift):
    alphabet = 'abcdefghijklmnopqrstuvwxyz'
    shifted_alphabet = alphabet[shift:] + alphabet[:shift]
    table = str.maketrans(alphabet + alphabet.upper(), shifted_alphabet + shifted_alphabet.upper())
    return plaintext.translate(table)

def decrypt_caesar(ciphertext, shift):
    return encrypt_caesar(ciphertext, -shift)

def main():
    while True:
        choice = input("Do you want to (E)ncrypt or (D)ecrypt a message? ").strip().upper()
        if choice in ('E', 'D'):
            break
        print("Invalid choice. Please enter 'E' to encrypt or 'D' to decrypt.")

    text = input("Enter the text: ").strip()
    shift = int(input("Enter the shift key (0-25): ").strip())

    if choice == 'E':
        encrypted_text = encrypt_caesar(text, shift)
        print(f"Encrypted text: {encrypted_text}")
    else:
        decrypted_text = decrypt_caesar(text, shift)
        print(f"Decrypted text: {decrypted_text}")

if __name__ == "__main__":
    main()
```

### How the Code Works

- **Encrypt Function** (`encrypt_caesar`):
  - Defines the alphabet as a reference.
  - Creates a shifted version of the alphabet based on the shift key.
  - Uses `str.maketrans` to create a translation table mapping each letter to its shifted counterpart.
  - Applies this translation table to the plaintext to get the ciphertext.
- **Decrypt Function** (`decrypt_caesar`):
  - Calls the `encrypt_caesar` function with a negative shift to reverse the encryption.
- **Main Function**:
  - Prompts the user to choose between encryption and decryption.
  - Accepts the text and shift key from the user.
  - Calls the appropriate function (`encrypt_caesar` or `decrypt_caesar`) and displays the result.

#### Code 2  
```python
def ceaser(text, shift_amount, direction):
  if shift_amount > 26:
    shift_amount = shift_amount % 26
  if direction == "encode":
    cipher_text = " "
    plain_text = text
    for letter in plain_text:
      position = alphabet.index(letter)
      new_position = position + shift_amount
      cipher_text += alphabet[new_position]
    print(f"The encoded text is {cipher_text}")
  elif direction == "decode":
    plain_text = ""
    cipher_text = text
    for letter in cipher_text:
      position = alphabet.index(letter)
      new_position = position - shift_amount
      plain_text += alphabet[new_position]
    print(f"The decoded text is {plain_text}")
  
my_flag = True
while(my_flag):   
  direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
  text = input("Type your message:\n").lower()
  shift = int(input("Type the shift number:\n"))

  ceaser(text,shift_amount = shift, direction = direction)

  my_choice = input("Do you want to play again? yes or no?")
  if my_choice == "no":
    my_flag = False
```

#### Code 3  

```python
alphabets = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
print("enter alphabets only !")
encode = input("enter txt to be encrypted: ").replace(" ","").casefold()
assert encode.isalpha(),"/* only alphabets allowed */"
shift = int(input("how many character would you like to shift: "))
encrypted_r =""
encrypted_l =""
for i in encode:
    index_r = (alphabets.index(i)+shift)%26
    encrypted_r += alphabets[index_r]
    index_l = (alphabets.index(i)-shift)%26
    encrypted_l += alphabets[index_l]
print("{} when shifted {} character form right: {}".format(encode,shift,encrypted_r))
print("{} when shifted {} character form left: {}".format(encode,shift,encrypted_l))

#caesar cipher decryption
decode = input("enter caesar cipher encoded text: ").replace(" ","").casefold()
assert decode.isalpha(),"/* only alphabets allowed */"
Shift = int(input("how may characters where shifted: "))
print("if shift was from left enter : l")
print("if shift was from right enter : r")
left_or_right = input("wether shift was from left or right: ").replace(" ","").casefold()
decrypted_r =" "
decrypted_l=" "
for k in decode:
    Index_r = (alphabets.index(k) - Shift) % 26
    decrypted_r += alphabets[Index_r]
    Index_l= (alphabets.index(k) + Shift) % 26
    decrypted_l += alphabets[Index_l]
if left_or_right == "l":
  print("{} when shifted {} character form left: {}".format(decode,shift,decrypted_l))
elif left_or_right== "r":
  print("{} when shifted {} character form right: {}".format(decode,shift,decrypted_r))
```

### Conclusion

The Caesar Cipher is a great starting point for learning about encryption. Its simplicity makes it easy to understand and implement, yet it introduces fundamental concepts used in more advanced cryptography. By following the steps outlined in this blog post, you can create your own Caesar Cipher program in Python and gain a deeper understanding of how encryption works.

💙 Happy coding and may your programs always compile flawlessly! 💙
