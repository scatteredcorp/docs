# Wallet
A wallet consists of a private key and a corresponding public key. It allows you to sign contracts on the platform and essentially replaces username/password authentication.

## Private keys

[ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) is a cryptographic algorithm used by BGC to sign contracts.  
BGC uses the [secp256k1](https://en.bitcoin.it/wiki/Secp256k1) elliptic curve.

A private key is a cryptographically secure random number between 1 and 2<sup>256</sup> - 2<sup>32</sup> - 2<sup>9</sup> - 2<sup>8</sup> - 2<sup>7</sup> - 2<sup>6</sup> - 2<sup>4</sup> - 1.

This number must be stored securely.

## Public keys

A public key is derived from the private key using ECDSA on the defined curve `secp256k1`.

## Address
Here is an overview on how to generate a BGC address.

### Step 1
Generate a private key.  
`36487317F7C3A171B8499114104A611CACB18E4FE03CB2BAB07C9B7C1AD83411`

#### Step 2
Compute the public key.  
`04B047580BD5F1E6D2113FFFD79A86B968343D241D0E963AEC0CB6363388C089887029CE4B9275C8A4A836B8258A663FAEEBA2F99C9EBC714C3108AF347410BBBF`

#### Step 3
Perform a SHA-256 hash on the public key.  
`D43E2A1B29E8E6FE84FD0C11FA627136FAD3AF27E6FFE8BA6FC16FA2067594C7`

#### Step 4
Perform a RipeMD hash on the SHA-256 hash.  
`10292A5EB397372B47E6715C8F9418D7B0F8A3BB`

#### Step 5
Add version byte in front of RipeMD hash (`0x8A`).  
`8A10292A5EB397372B47E6715C8F9418D7B0F8A3BB`

#### Step 6
Perform double SHA-256 hash of the versioned hash (Step 5).  
`FB446099A2167287F02265E8BA2D8A460F13A4E35F437D53C525E331B541FC76`

#### Step 7
Take the first 4 bytes of the double SHA-256 hash.  
Checksum: `FB446099`  

#### Step 8
Append checksum to the versioned hash from step 5.  
`8A10292A5EB397372B47E6715C8F9418D7B0F8A3BBFB446099`  
This is the 25 bytes address.

#### Step 9
Encode result to a Base58 string.  
`xZ7h1HUEcraAAHiJBqm1aDnr9nXJBh6yz8`