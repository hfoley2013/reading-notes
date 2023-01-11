# Cryptography

## Reading

* [Encryption, Decryption & Hacking](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)
* [Ceasar Cipher](https://en.wikipedia.org/wiki/Caesar_cipher)
* [VIDEO: Cryptography Crash Course](https://www.youtube.com/watch?v=jhXCTbFnK8o)

## Additional Resources

* [Introduction to Cryptography](https://thebestvpn.com/cryptography/)
* [How Computers Generate Random Numbers](https://www.howtogeek.com/183051/htg-explains-how-computers-generate-random-numbers/)

## Notes

### Basic Definitions

* **Encryption:** scrambling the data according to a secret key (in this case, the alphabet shift).
* **Decryption:** recovering the original data from scrambled data by using the secret key.
* **Code cracking:** uncovering the original data without knowing the secret, by using a variety of clever techniques.
* **Polymorphism:** a cipher that changes itself with each use.

### Types of Cryptography

* **Symmetric-key cryptography**
  * AKA: Secret-key cryptography
  * Uses the same key for both encryption and decryption.
  * Examples of symmetric-key algorithms include `AES` and `DES`.
* **Asymmetric-key cryptography**
  * AKA: Public-key cryptography
  * Uses a pair of keys for encryption and decryption.
    * One key, known as the public key, is used for encryption and the other key, known as the private key, is used for decryption.
  * Examples of asymmetric-key algorithms include `RSA` and `elliptic curve cryptography`.
* **Hash functions**
  * AKA: Message digests
  * A type of cryptography that take an input (or 'message') and return a fixed-size string of characters, which is usually a 'digest' that is unique to the unique message.
    * This can be used for example for checking the integrity of a message or file, verifying a digital signature, etc.
  * Examples of hash functions include `SHA-256` and `MD5`.

### SHA-256

SHA-256 (Secure Hash Algorithm 256-bit) is a cryptographic hash function that takes an input (or 'message') and returns a fixed-size string of characters, which is a 'digest' that is unique to the unique data that was input. It is a member of the SHA-2 cryptographic hash functions designed by the National Security Agency (NSA). It is a one-way function, meaning it is practically impossible to determine the original input data from its resulting hash value, and any small change in the input data will result in a vastly different output hash.

It's commonly used to confirm that data has been transmitted or stored without errors, check the integrity of files, and it also use in different application like password hashing, digital signatures, and other security protocols.

#### Basic Code Example

```py
import hashlib

data = "This is the data to be hashed."

# Create a new SHA-256 hash object
sha256 = hashlib.sha256()

# Update the hash object with the bytes of the data
sha256.update(data.encode())

# Get the hexadecimal representation of the hash
hash_value = sha256.hexdigest()

print(hash_value)
```

This code first imports the `hashlib` library, which provides the SHA-256 hashing function. Then, it defines some data (in this case, a string) that we want to hash.

It then creates a new SHA-256 hash object using the `hashlib.sha256()` function.

The `update()` method is then used to feed the data (in bytes format) into the hash object, and calculate the hash. The resulting hash is stored in the variable `hash_value` which is in hexadecimal format that can be used to represent the hash in a readable format.

You can also use `.digest()` to get the bytes version of the hash.

```py
hash_value = sha256.digest()
```

#### Advanced Code Example

In a more sophisticated example, you might use the SHA-256 algorithm in combination with a salt, to make the resulting hash even more secure.

A salt is a random string of characters that is generated and added to the original data before hashing it. The salt is then stored in a separate location (such as a database) and is used in conjunction with the original data to verify the authenticity of the user's input.

The primary purpose of a salt is to ensure that the same input (e.g. "password123") will result in a different hash output each time it's hashed. This helps to protect against precomputed hash attacks, in which an attacker precomputes a large number of hash values for commonly-used inputs, and then compares them to a target hash value in order to quickly identify a match.

Salts are also commonly used in password storage. When a user sets their password, the plaintext password is concatenated with a randomly generated salt, and then hashed. The salt and the resulting hash are then stored together in the database.

The salt is stored separately from the hashed password, so it can be used later to verify the user's input.
When the user later attempts to log in by entering their password, the system retrieves the stored salt and uses it along with the entered password to calculate a new hash. If this new hash matches the one stored in the database, the password is considered to be correct.

The use of a salt increases the complexity of the hash function and makes it harder for an attacker to crack the password even if they manage to obtain the hashed password, this is because they would have to guess the correct salt in order to be able to calculate the correct password hash.

In summary, the salt's main purpose is to add an extra layer of security by making it more difficult to use precomputed hash tables or dictionary attacks to crack hashed passwords, and making each user's password appear different even if they have the same plaintext password.

Here's an example that shows how to hash a password using SHA-256 and a salt in Python:

```py
import hashlib, os

password = "correct horse battery staple".encode()

# Create a new salt
salt = os.urandom(16)

# Create a new SHA-256 hash object
sha256 = hashlib.sha256()

# Update the hash object with the salt and the password
sha256.update(salt + password)

# Get the hexadecimal representation of the hash
password_hash = sha256.hexdigest()

# Store the salt and the password hash in a database (or wherever it's appropriate)
# ...

# To verify the user's input
user_password = "correct horse battery staple".encode()
user_salt = salt

# Create a new SHA-256 hash object
sha256 = hashlib.sha256()

# Update the hash object with the user's salt and the user's password
sha256.update(user_salt + user_password)

# Get the hexadecimal representation of the user's hash
user_password_hash = sha256.hexdigest()

# Compare the password hash stored in the database with the user's password hash
if password_hash == user_password_hash:
    print("Password is correct.")
else:
    print("Wrong Password.")
```

In this example, when a user first sets a password, a salt is generated using the `os.urandom()` function, which returns cryptographically secure random bytes. The salt and the password are then concatenated, hashed using SHA-256 and stored in the database along with the salt.

When the user later attempts to log in by entering their password, the system retrieves the stored salt and uses it along with the entered password to calculate a new hash. If this new hash matches the one stored in the database, the password is considered to be correct.

Using a salt to hash a password in this way makes it much more difficult for an attacker to crack the password even if they manage to obtain the hashed password. This is because they would have to guess the correct salt in order to be able to calculate the correct password hash.

This is a simple example, you would use a more sophisticated way like using bcrypt or scrypt instead of sha256 to hash your passwords, because these are designed to be much harder to crack with specialized hardware, and they also have built-in ways of handling the salt, making it more secure.
