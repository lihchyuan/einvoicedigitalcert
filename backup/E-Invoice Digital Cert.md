# E-Invoice Digital Certificate

As the e-Invoice mandate in Malaysia rapidly approaches, it is essential for businesses to understand the digital signature process. According to guidelines from the Inland Revenue Board of Malaysia (IRBM), also known as Lembaga Hasil Dalam Negeri Malaysia (LHDNM), each invoice submission requires a digital signature. Whether submitting a single invoice or a batch, every individual invoice must be digitally signed to comply with regulations.

# Let’s explore the digital signature process in more detail:

## What is a Digital Signature?

A digital signature acts as a virtual seal, uniquely linking digital information to its creator. Similar to a handwritten signature or a stamped seal in the physical world, a digital signature offers enhanced security and reliability in the digital realm.

A digital signature consists of two key components: a private key and a public key. These keys are mathematically linked through asymmetric encryption algorithms such as RSA (Rivest-Shamir-Adleman) or ECC (Elliptic Curve Cryptography), ensuring that data encrypted with one key can only be decrypted with the other.

### Importance and Applications of Digital Signatures:

- Authentication: Digital signatures authenticate the sender's identity, ensuring the message or document originates from a legitimate source.
- Integrity: Digital signatures detect any alterations or tampering attempts, ensuring the integrity of transmitted data.
- Non-repudiation: Once a document is digitally signed, the sender cannot deny their involvement or repudiate the contents, providing irrefutable proof of their consent or authorization.
- Legal Validity: In many jurisdictions, digital signatures hold the same legal validity as handwritten signatures, facilitating the execution of contracts, agreements, and other legally binding documents electronically.

## The Role of Certificate Authorities (CAs):

Certificate Authorities (CAs) are crucial in validating digital signatures by providing a trusted framework for verifying the authenticity and legitimacy of public keys associated with digital certificates. Here's how CAs facilitate the validation process:

- Issuance of Digital Certificates: CAs issue digital certificates, electronic credentials that bind an individual or entity's identity to a public key.
- Verification of Identity: CAs rigorously verify the identity of the requesting entity before issuing a digital certificate.
- Binding Public Keys to Identities: After identity verification, the CA digitally signs the digital certificate, attesting that the public key is associated with the verified identity.
- Distribution of Certificates: CAs make digital certificates publicly available through online repositories, enabling relying parties to access and verify certificate validity.
- Validation of Digital Signatures: Recipients extract the digital signature and the signer's digital certificate to verify authenticity using the CA's public key.
- Trust Chain Verification: Recipients can recursively validate the certificate chain to ensure each certificate is valid and issued by a trusted CA.

## How it Works for e-Invoicing in Malaysia:

1. Generating e-Invoices: Taxpayers or e-Invoice intermediaries generate e-Invoices in XML or JSON format.
2. Hash Calculation: Using the SHA 256 algorithm, calculate the hash value of the e-Invoice.
3. Digital Signature: Digitally sign the hash of the invoice with the digital certificate.
4. Invoice Submission: Include the signature value in the e-Invoice XML/JSON and submit it to IRBM/LHDNM APIs.

## Validating Digital Signatures by IRBM/LHDNM:

1. Decryption and Identification: IRBM decrypts the signature value using the taxpayer's public key and identifies the hash value.
2. Hash Comparison: IRBM calculates the hash of the e-Invoice XML and compares it with the decrypted hash value. If they match, the invoice is considered valid; otherwise, it is deemed invalid.