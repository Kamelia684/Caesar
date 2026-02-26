# Caesar
# caesar_cipher.py

def encrypt(text: str, shift: int) -> str:
    """Encrypt text using Caesar cipher with given shift."""
    encrypted = ""
    for char in text:
        if char.isalpha():
            # Determine offset for uppercase/lowercase
            offset = 65 if char.isupper() else 97
            encrypted += chr((ord(char) - offset + shift) % 26 + offset)
        else:
            encrypted += char
    return encrypted

def decrypt(cipher: str, shift: int) -> str:
    """Decrypt text encrypted with Caesar cipher."""
    return encrypt(cipher, -shift)

if __name__ == "__main__":
    sample_text = "Hello, OpenAI!"
    shift_value = 3
    cipher = encrypt(sample_text, shift_value)
    print(f"Encrypted: {cipher}")
    print(f"Decrypted: {decrypt(cipher, shift_value)}")
