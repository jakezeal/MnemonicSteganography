# Encrypted Mnemonic Codes and a better UX with Stenography

Mainstream adoption requires easy security. Instead of writing down a 12 word code, save an image with encrypted data

# Supported Languages

* [Swift](https://github.com/jakezeal/MnemonicSteganography/tree/master/mnemonic-steganography-swift)

## Inspiration

We are solving the biggest problem in cryptocurrency mainstream adoption - user experience and security.

In 2013, Bitcoin's [BIP-39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) added mnemonic codes. This made backing up, storing and securing cryptocurrencies much easier for humans. While this was an innovation in security and user experience, it is still a UX nightmare. Onboarding requires new users to write down and verify a list of 12 or 24 words. Only after writing these words on a piece of paper, can a user feel safe and confident about using their new wallet. On mobile, many apps do not even allow the encryption of these mnemonic codes - in large part because it will worsen the UX even further. Due to these UX hurdles and fear in the security, many new Bitcoiners and crypto users will opt in to centralized, 3rd party services to store their keys. Instead of having a user write down their mnemonic code that they will only use to recover funds, perhaps months or years later, we are proposing a new standard.

## What it does

CryptoImage introduces a new security standard for crypto backups on mobile. We are an open source project and library that dramatically improves user experience. Instead of having to write down and verify a traditional [mnemonic code](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) as a part of onboarding, you can now save and verify your code / private key using an image. Using [steganography](https://en.wikipedia.org/wiki/Steganography), we are able to encrypt a mnemonic code, encode the encrypted string into an image, and have a functional way to backup and restore mnemonic codes via image files. 

## How we built it

We started by researching the possible ways we could replace or improve the user experience of mnemonic codes. This lead us to the idea of using stenography in images to encrypt and encode the data. 

1. Create an open source library for steganography in Swift (iOS)
Involves low level bit manipulation, pixel manipulation, memory management, encrypting/decrypting data, encoding/decoding data, pointers in swift & interacting with low-level C apis.
2. Fork [BreadWallet](https://github.com/breadwallet/breadwallet-ios) - a popular open source iOS bitcoin wallet
Add features to
- Backup an encrypted mnemonic code with encoded data using our [open source library](https://github.com/jakezeal/MnemonicSteganography/tree/master/mnemonic-steganography-swift)
- Recover a wallet by uploading an image with an encoded mnemonic code 
3. [In progress] Creating CocoaPod/Carthage (dependency management) for even easier installation in iOS

## Challenges we ran into 

1. Research and discover the idea and it's potential
1. Complex bit & pixel manipulation
1. Working with low-level pointers in Swift (the APIs are abnormal)
2. Create an entire open source library to support encoding and decoding of images with arbitrary data in iOS
3. Low-level APIs to encode/decode & encrypt/decrypt data
5. Understand BIP39 
6. Dive into a large codebase with very little documentation ([BreadWallet iOS app](https://github.com/breadwallet/breadwallet-ios)
7. Forking the codebase and having to implement complex changes and encryption of mnemonic codes
8. Limitations of iOS / Swift APIs
9. Saving an image on iOS without compression

## Accomplishments that we're proud of

1. Create a functional open source project for backing up mnemonic codes with steganography
2. Research and discover a way to dramatically improve user experience in the security of mnemonic codes (especially on mobile)
3. Overcome many challenges such as complex bit & pixel manipulation, low level pointers in Swift, encoding/decoding data into an image
4. Forking and diving into a large codebase with very little documentation
5. Creating a functional Bitcoin wallet with our open source library integration
6. Integrating our open source library

## What we learned

1. Complex bit manipulation and pixel manipulation in Swift
2. Working with pointers in Swift (the APIs are abnormal)
3. Structuring an open source project
4. Dive into a large codebase with very little documentation ([BreadWallet iOS app](https://github.com/breadwallet/breadwallet-ios)
5. Adding additional features to mnemonic codes
6. Bitcoin improvement proposals
7. New ways to ensure data security
8. Exploring ways to easily integrate an open source project / library

## What's next for CryptoImage - Secure mnemonic seeds with steganography

The evolution of CryptoImage, and improving UX in security is exciting:
- Multi-sig images (export several images with parts of the private key / mnemonic code)
- Add [salt](https://en.wikipedia.org/wiki/Salt_(cryptography)) for extra layer of security in encoded image
- Share on airdrop
- Architecture improvements - simple function to call UIImage.encoder(with: mnemonic code string)

Stretch:
- Future Bitcoin wallet which introduces CryptoImage as a secure form of backup on mobile
- Integrate Lightning into our Bitcoin wallet to have Venmo-like payments (fast transactions, great UX, send via usernames)
- Buy and sell Bitcoin directly from the app

We want to make using Bitcoin and securing backups as easy and stress-free as using Venmo.


## Extras

1. Ask user for encryption password & encrypt mnemonic code
2. Encode mnemonic code into image (using stenography)
3. Export image to camera roll
4. Verify by uploading and decoding image

Note:
- Encoded image with mnemonic code data must be store uncompressed 
