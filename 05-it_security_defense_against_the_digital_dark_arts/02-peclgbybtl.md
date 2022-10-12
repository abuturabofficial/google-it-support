# Symmetric Encryption

## Cryptography

The cryptography has two main fields:

  + Cryptology: The study of cryptographic methods.
  + Cryptanalysis: The study of breaking the cryptography.

### Encryption

The act of taking a message, called **plaintext**, and applying an operation to it, called a **cipher**, so that you receive a garbled, unreadable message as the output, called **ciphertext**.

The reverse is **Decryption**.

The Cipher is made up of two components:

  + Encryption algorithm
  + Key

### Encryption algorithm

The underlying logic of the process that's used to convert the plaintext into ciphertext.

These algorithms are usually very complex. But there are also simple algorithms as well.

![](images/Pasted%20image%2020221012084503.png)

**Security through obscurity** is a principle where underlying encryption algorithm is also kept hidden for security purposes. But you shouldn't rely on it, as once the underlying mechanism is discovered, your whole security will wash away.

The underlying principle of cryptography is called **Kirchhoff's principle**.

### Cryptosystem

A collection of algorithms for key generation and encryption and decryption operations that comprise a cryptographic service should remain secure – even if everything about the system is known, except the key.

  + The system should remain secure even if your adversary knows exactly what kind of encryption systems you're employing, as long as your **keys remain secure.**

### Frequency analysis

The practice of studying the frequency with which letters appear in a ciphertext.

An Arab mathematician of 9th century, used this first cryptographic method

### Steganography

The practice of hiding the information from observers, but not encoding it.

  + The writing of messages with invisible ink.
  + The modern steganographic techniques involves, hiding the code/scripts in the PDF or image files etc.

## Types of cryptanalysis attack

### Known-Plaintext Analysis (KPA)

Requires access to some or all the of the plaintext of the encrypted information. The plaintext is not computationally tagged, specially formatted, or written in code. The analyst's goal is to examine the known plaintext to determine the key used to encrypt the message. Then they use the key to decrypt the encoded information.

### Chose-Plaintext Analysis (CPA)

Requires that the attacker knows the encryption algorithm or has access to the device used to do the encryption. The analyst can encrypt one block of chosen plaintext with the targeted algorithm to get information about the key. Once the analyst obtains the key, they can decrypt and use sensitive information. 

### Ciphertext-Only Analysis (COA)

 Requires access to one or more encrypted messages. No information is needed about the plaintext data, the algorithm, or data about the cryptographic key. Intelligence agencies face this challenge when intercepting encrypted communications with no key.

### Adaptive Chosen-Plaintext attack (ACPA)

ACPA is similar to a chosen-plaintext attack. Unlike a CPA, it can use smaller lines of plaintext to receive its encrypted ciphertext and then crack the encryption code using the ciphertext.

### Meddler-in-the-Middle (MITM)

MITM uses cryptanalysts to insert a meddler between two communication devices or applications to exchange their keys for secure communication. The meddler replies as the user, and then performs a key exchange with each party. The users or systems think they communicate with each other, not the meddler. These attacks allow the meddler to obtain login credentials and other sensitive information.

[Wikipedia article on Cryptanalysis](https://en.wikipedia.org/wiki/Cryptanalysis)
[Integer Factorization](https://en.wikipedia.org/wiki/Integer_factorization)
[Cryptanalysis explained](https://www.comparitech.com/blog/information-security/cryptanalysis/)

## Symmetric Cryptography

These types of algorithms use the same key for encryption and decryption.

### Substitution cipher

An encryption mechanism that replaces parts of your plaintext with ciphertext.

  + E.g., Caesar cipher, ROT13 etc.

![](images/Pasted%20image%2020221012142847.png)

### Stream cipher

Takes a stream of input and encrypts the stream one character or one digit at a time, outputting one encrypted character or digit at a time.

  + Initialization vector (IV) is used, to add a random string of characters to the key.

### Block ciphers

The cipher takes data in, places it into a bucket or block of data that's a fixed size, then encodes that entire block as one unit.

![](images/Pasted%20image%2020221012143255.png)

## Symmetric Encryption Algorithms

### Data Encryption Standard (DES)

One of the earliest standard is **Data Encryption Standard (DES)**.

  + With input from NSA, IBM developed it in the 1970s.
  + It was used as a FIPS.
  + Used 64-bits key sizes.

### FIPS

Federal Information Processing Standard.

### Standard Encryption Standard (AES)

**NIST** (National Institute of Standards and Technology), adopted **Advanced Encryption Standard (AES)** in 2001.

  + 128-blocks, twice the size of DES blocks, and supports key length of 128-bits, 192-bits, or 256-bits.
  + Because of the large key size, brute-force attacks on AES are only theoretical right now, because the computing power required (or time required using modern technology) exceeds anything feasible today.

An important thing to keep in mind when considering various encryption algorithms is **speed**, and **ease of implementation**.

### RC4 (Rivest Cipher 4)

A symmetric stream cipher that gained widespread adoption because of its simplicity and speed.

  + Abandoned due to inheritance weaknesses.

![](images/Pasted%20image%2020221012144928.png)

[RC4 Exists No More](https://www.rc4nomore.com/)

# Public Key or Asymmetric Encryption

## Asymmetric Cryptography

Asymmetric or Public Key ciphers.

Two different keys are used for encryption and decryption.

The three concepts that an asymmetric cryptosystem grants us are:

  + Confidentiality
  + Authenticity
  + Non-repudiation

Symmetric encryption is used for key exchange.

### Message Authentication Codes or MACs

A bit of information that allows authentication of a received message, ensuring that the message came from the alleged sender and not a third party.

#### HMAC

Keyed-hash messaged authentication code.

### CMACs

Cipher-Based Message Authentication Codes.

#### CBC-MAC

Cipher block chaining message authentication codes.

## Asymmetric Encryption Algorithms

### RSA

The first practical asymmetric cryptography systems to be developed is **RSA**.

Pretty complex math is involved in generating key pair for RSAs.

This crypto system was patented in 1983 and was released to the public domain by RSA Security in the year 2000. 
  
### Digital Signature Algorithm or DSA

It was patented in 1991, and is part of the US government's Federal Information Processing Standard.

Similar to RSA, the specification covers the key generation process along with the signing and verifying data using the key pairs. It's important to call out that the security of this system is dependent on choosing a random seed value that's incorporated into the signing process. If this value was leaked or if it can be inferred if the prime number isn't truly random, then it's possible for an attacker to recover the private key.

### Diffie-Hellman

Named after coworkers, invented it. It is solely used for key exchange.

Let's assume we have two people who would like to communicate over an unsecured channel, and let's call them Suzanne and Daryll. First, Suzanne and Daryl agree on the starting number that would be random and will be a very large integer. This number should be different for every session and doesn't need to be secret. Next, each person decides another randomized large number, but this one is kept secret. Then, they combine their shared number with their respective secret number and send the resulting mix to each other. Next, each person combines their secret number with the combined value they received from the previous step. The result is a new value that's the same on both sides, without disclosing enough information to any potential eavesdroppers to figure out the shared secret. This algorithm was designed solely for key exchange, though there have been efforts to adapt it for encryption purposes. 

### Elliptic curve cryptography (ECC)

A public-key encryption system that uses the algebraic structure of elliptic curves over finite fields to generate secure keys.

![](images/Pasted%20image%2020221012152354.png)

  + The benefit of elliptic curve based encryption systems is that they are able to achieve security similar to traditional public key systems with smaller key sizes. So, for example, a 256 bit elliptic curve key, would be comparable to a 3,072 bit RSA key. This is really beneficial since it reduces the amount of data needed to be stored and transmitted when dealing with keys. 
  + Both Diffie-Hellman and DSA have elliptic curve variants, referred to as **ECDH** and **ECDSA**, respectively.
  + The US NEST recommends the use of EC encryption, and the NSA allows its use to protect up to top secret data with 384 bit EC keys
  + But, the NSA has expressed concern about EC encryption being potentially vulnerable to quantum computing attacks, as quantum computing technology continues to evolve and mature.

[Sony PlayStation 3: An asymmetric encryption attack in 2010](https://nakedsecurity.sophos.com/2012/10/25/sony-ps3-hacked-for-good-master-keys-revealed/)

# Hashing
A type of function or operation that takes in an arbitrary data input and maps it to an output of fixed size, called a hash or digest.

![](images/Pasted%20image%2020221012160358.png)

  + You feed in any amount of data into a hash function, and the resulting output will always be the same size. But the output should be **unique to the input**, such that two different inputs should never yield the same output.
  + Hashing can also be used to identify duplicate data sets in databases or archives to speed up searching tables, or to remove duplicate data to save space.
  + Cryptographic hashing is distinctly different from encryption because cryptographic hash functions should be one directional.
+ The ideal cryptographic has function should be **deterministic**, meaning that the same input value should always return the same hash value.
+ The function should not allow **Hash collisions**.

### Hash collisions

Two different inputs mapping to the same output.

![](images/Pasted%20image%2020221012161018.png)

## Hashing Algorithms

### MD5

Designed in early 1990s. Operates on 512-bits block and generates 128-bits hash digest.

  + While MD5 was designed in 1992, a design flaw was discovered in 1996, and cryptographers recommended using the **SHA-1** hash.
  + In 2004, it was discovered that is MD5 is susceptible to hash collisions.
  + In 2008, security researchers create a fake SSL certificate that was validated due to MD5 hash collision.
  + Due to these very serious vulnerabilities in the hash function, it was recommended to stop using MD5 by 2010.
  + In 2012, this hash collision was used for nefarious purposes in the flame malware, which used to forge a Microsoft digital certificate to sign their malware, which resulted in the malware appearing to be from legitimate software that came from Microsoft.

### SHA-1

SHA-1 is part of the Secure Hash Algorithm suite of functions, designed by the NSA, published in 1995.

During the 2000s, a bunch of [theoretical attacks](https://eprint.iacr.org/2005/010) against SHA1 were formulated, and some [partial collisions](https://eprint.iacr.org/2007/474) were demonstrated.

  + Operated at 512-bits blocks and use 160-bits hash digest.
  + It is used in popular protocols like:
    + TLS/SSL
    + PGP SSH
    + IPsec
    + VCS like git
  + NIST recommended stopping the use of SHA-1, and relying on SHA-2 in 2010.
  + Major browsers vendor dropped support for SSL certificates that use SHA-1 in 2017.
  + In early 2017, [full collision of SHA-1](https://shattered.io/) was published. Two PDFs were created with same SHA-1 hashes.
  + **MIC or Message Integrity Check** to make sure there is no data corruption in transit to the hash digest.

### Defense against hash attacks

The passwords should not be stored in plaintext, instead they should be hashed and, store a hash.

  + Brute-force attack against a password hash can be pretty computationally expensive, depending upon the hash system used.
  + A successful brute force attack, against even the most secure system imaginable, is a function of attacker time and resources.
  + Another common methods to help raise the computational bar and protect against brute force attacks is to run the password through the hashing function multiple times, sometimes through thousands of iterations.
  + A **rainbow** table is ta table of precalculated hashes.

![](images/Pasted%20image%2020221012174138.png)

  + To protect against these precalculated rainbow tables, **password salt** come into play.

### Password salt

Additional randomized data that's added into the hashing function to generate a hash that's unique to the password and salt combination.

  + Modern systems use 128-bits salt.
  + It means there are 2^128 possible salt combination.

![](images/Pasted%20image%2020221012173813.png)

# Cryptographic Applications

## Public Key Infrastructure (PKI)

PKI is a system that defines the creation, storage, and distribution of digital certificates. A digital certificate is a file that proves that an entity owns a certain public key.

  + The entity responsible for storing, issuing, and signing digital certificates is call **Certificate authority or CA**.
  + There's also a **Registration authority, or RA**, that's responsible for verifying the identities of any entities requesting certificates to be signed and stored with the CA.
  + A central repository is needed to securely store and index keys, and a certificate management system of some sort makes managing access to stored certificates and issuance of certificates easier.

### PKI signing process

Start from the Root Certificate authority, which signs the certificate itself, as no one above it.

![](images/Pasted%20image%2020221012212253.png)

This Root certificate authority can now use the self-signed certificate and the associated private key to begin signing other public keys and issuing certificates.

![](images/Pasted%20image%2020221012211048.png)

A certificate that has no authority as a CA is referred to as an **end-entity** or **leaf certificate**.

  + The [X.509 standard](https://www.ietf.org/rfc/rfc5280.txt) is what defines the format of digital certificates.

The fields defined in X.509 are:

#### Version
What version of the X.509 standard the certificate adheres to.

#### Serial number

A unique identifier for the certificate assigned by the CA, which allows the CA to manage and identify individual certificates.

#### Certificate Signature Algorithm

This field indicates what public key algorithm is used for the public key and what hashing algorithm is used to sign the certificate.

#### Issuer Name

This field contains information about the authority that signed the certificate.

#### Validity

This contains two subfields – “Not Before” and “Not After” – which define the dates when the certificate is valid for.

#### Subject

This field contains identifying information about the entity the certificate was issued to.

#### Subject Public Key Info

These two subfields define the algorithm of the public key, along with the public key itself.

#### Certificate Signature Algorithm

Same as the Subject Public Key Info field; These two fields must match.

#### Certificate Signature Value

The digital signature data itself.

### SSL/TLS server certificate

This is a certificate that a web server presents to a client as part of the initial secure setup of an SSL, TLS connection.

![](images/Pasted%20image%2020221012211653.png)

### Self-signed certificate

Signed by the same entity that issued the certificate. Signing your own public key using your own with private key.

### SSL/TLS client certificate

As the names implies, these are certificates that are **bound to clients** and are used to **authenticate** the client to the server, allowing access control to an SSL/TLS service.

### Code Signing Certificates

This allows users of these signed applications to verify the signatures and ensure that the application was not tampered with.
 
### Webs of Trust

Individuals are signing each other certificates, after verifying the identity of the persons with agreed upon methods.

![](images/Pasted%20image%2020221012213520.png)

## Cryptography in Action

### HTTPS

The secure version of HTTP, the Hyper Text Transport Protocol.

  + It can also be called HTTP over the TLS.
  + Even though, TLS is a completely independent protocol from HTTPS.

### TLS

It grants us three things

  1) A secure communication line, which means data being transmitted, is protected from potential eavesdroppers.
  2) The ability to **authenticate** both parties communicating, though typically only the server is authenticated by the client.
  3) The **integrity** of communications, meaning there are checks to ensure that messages aren't lost or altered in transit.

To establish a TLS channel, there is a TLS handshake in place.

![](images/Pasted%20image%2020221012214311.png)

The session key is the shared symmetric encryption key used in TLS sessions to encrypt data being sent back and forth.

### Secure Shell (SSH)

A secure network protocol that uses encryption to allow access to a network service over unsecured networks.

  + SSH uses public key cryptography.

### Pretty Good Privacy (PGP)

An encryption application that allows authentication of data, along with privacy from third parties, relying upon asymmetric encryption to achieve this.

## Securing Network Traffic

### Virtual Private Network (VPN)

A mechanism that allows you to remotely connect  a host or network to an internal, private network, passing the data over a public channel, like the internet.

![](images/Pasted%20image%2020221012215407.png)

There are different VPN protocols:

  + IPsec

![](images/Pasted%20image%2020221012215516.png)

IPsec support two modes:

  1) When **transport mode** is used, only the payload of the IP packet is encrypted, leaving the IP headers untouched.
  2) In **tunnel mode**, the entire IP packet, header payload and all, is encrypted and encapsulated inside a new IP packet with new headers.

  + Layer 2 tunneling protocol or L2TP

It is not an all alone protocol, it is used in conjunction with IPsec protocol.

The **tunnel** is provided by L2TP, which permits the passing of unmodified packets from one network to another. The **secure channel**, on the other hand, is provided by IPsec, which provides confidentiality, integrity, and authentication of data being passed.

The combination of L2TP and IPsec is referred to as **L2TP/IPsec** and was officially standardized in [IETF RFC 3193](https://tools.ietf.org/html/rfc3193)

  + OpenVPN

OpenVPN is an example of LT2p/IPsec.

It uses OpenSSL library to handle key exchange and encryption of data, along with control channels.

OpenVPN can operate over either TCP or UDP, typically over port 1194.

It can either rely on a Layer 3 IP tunnel or a Layer 2 Ethernet tap. The Ethernet tap is more flexible, allowing it to carry a wider range of traffic. 

OpenVPN supports up to 256-bits encryption through OpenSSL library. It runs in user space, so avoid the underlying vulnerabilities of the system.

## Cryptographic Hardware

### TPM or Trusted Platform Module

Another interesting application of cryptography concepts, is the **Trusted Platform Module or TPM**. This is a hardware device that's typically integrated into the hardware of a computer, that's a dedicated crypto processor.

TPM offers:

  + Secure generation of keys
  + Random number generation
  + Remote attestation
  + Data binding and sealing

**There's been a report of a [physical attack on a TPM](https://gcn.com/Articles/2010/02/02/Black-Hat-chip-crack-020210.aspx) which allowed a security researcher to view and access the entire contents of a TPM**.

For **Full disk encryption or FDE**, we have the number of options:

  + PGP
  + BitLocker
  + Filevault 2
  + dm-crypt

![](images/Pasted%20image%2020221012222043.png)

