# otp-messenger-idea
System Design v1.0

Smart contract side with Secret Network:
- Receives submitted Kyber and Dilithium PKs
- Wrap random one time pad key around Kyber 
- Send it to a pair of clients attached with the Kyber PK, Dilithium PK, Wallet ID of themselves and Wallet ID of the other user and Signature

Client side:
- User enters service through Tor network
- User generates Kyber and Dilithium keys locally
- Either user enters wallet ID of the person they want to chat with
- User deposits X cryptocurrency then swaps using zk proofs to Secret Network & Nym Network coins for a pool
- Both users submit Kyber and Dilithium public keys and the wallet ID of the person they want to chat with
- Both users receive a truly random one time pad key 
- XOR bitwise operations using the one time pad key to transmit the message through the server of the admin (or p2p without admin)
- The receiving side decrypts the message and destroys the one time pad key 
- To send a message again, both users request a truly random one time pad key again and repeat the process

Open for improved ideas & implementation. 

OTP requirements:
1) Key gets destroyed
2) Truly random (RDRAND and RDSEED are Intel Secure Key technology)
3) Plaintext = key length, 32 bytes, but can be increased
4) Key is securely distributed with Kyber/Dilithium. 
