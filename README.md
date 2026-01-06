import random
import string

def generate_password(length):
    if length < 4:
        print("Password length must be at least 4")
        return

    letters = string.ascii_letters      # a-z A-Z
    digits = string.digits              # 0-9
    symbols = string.punctuation        # !@#$%^&*()

    all_chars = letters + digits + symbols

    password = ''.join(random.choice(all_chars) for _ in range(length))
    return password

def main():
    print("=== Password Generator ===")

    try:
        length = int(input("Enter password length: "))
        password = generate_password(length)

        if password:
            print("Generated Password:", password)

    except ValueError:
        print("Please enter a valid number")

if __name__ == "__main__":
    main()
