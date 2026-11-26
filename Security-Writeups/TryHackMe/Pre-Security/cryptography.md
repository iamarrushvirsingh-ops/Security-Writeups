# Cryptography

- Cryptography is used to encrypt messages and information so that if they are intercepted, they can't be read by people who weren't meant to read them.

## Key Terms

- **Plaintext**: A message you can read normally, like `HELLO` or `Patient name: Alice Smith`.
- **Ciphertext**: The scrambled version that isn't supposed to make sense, like `KHOOR` or `Sdwlhqw qdph: Dolfh Vplwk`.
- **Key**: The secret value that controls how the scrambling and unscrambling work. Think of it as a password the algorithm uses.
- **Algorithm**: The public set of steps that explains how the key is used on the message. Everyone can know the algorithm; the security comes from keeping the key secret.

## Symmetric Encryption

- In this type of encryption, a single secret key is used to both encrypt and decrypt data.
- Very fast and light on computer resources.
- The only problem is sharing the secret key safely over the internet.

## Asymmetric Encryption

- This type of encryption uses a mathematically linked pair of keys: a public key and a private key.
- The public key is used to encrypt the message, and only the matching private key can decrypt it.
- It is slower and needs more computing power.
- Fun fact: if you encrypt something with your private key, it can be decrypted using your public key. This idea is used for digital signatures.
- Its most common use is in HTTPS.

## How HTTPS Uses Both

Here's what happens when you visit `https://google.com`:

1. Your browser asks the website for its public key.
2. The website sends back its public key inside a **certificate** (explained below).
3. Your browser and the website use asymmetric encryption to agree on a shared secret (a symmetric key), without anyone else being able to see it.
4. From then on, they switch to fast **symmetric encryption** using that shared secret for the rest of the session.

This combination is called a **hybrid approach**:

- **Asymmetric encryption** solves the problem of sharing the key.
- **Symmetric encryption** does the heavy lifting because it's much faster.

## Certificates

How does your browser know a public key really belongs to the website, and not to an attacker pretending to be it? That's what **certificates** are for.

A certificate is a digital document that:

- Contains the website's public key.
- States who the key belongs to (like `example.com`).
- Is digitally signed by a trusted organisation called a **Certificate Authority (CA)**.

Your browser and operating system come with a built-in list of trusted CAs. When a website sends its certificate, the browser checks:

- That a trusted CA signed it.
- That it's still valid (not expired or revoked).
- If everything checks out, the browser shows the padlock and trusts the public key.
