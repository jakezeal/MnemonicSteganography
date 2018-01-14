# Encrypted Mnemonic Codes and a better UX with Stenography

Encrypt and encode your mnemonic code into an image using stenography. A new standard for mainstream Bitcoin storage on mobile.

Implement into any existing crypto wallet that supports [BIP0039](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki). Instead of having a user write down 12 or 24 words, export an image. 

# Contents

* [Swift](mnemonic-stenography-swift)
* [Python](mnemonic-stenography-python)

1. Ask user for encryption password & encrypt mnemonic code
2. Encode mnemonic code into image (using stenography)
3. Export image to camera roll
4. Verify by uploading and decoding image

Note:
- Encoded image with mnemonic code data must be store uncompressed 
