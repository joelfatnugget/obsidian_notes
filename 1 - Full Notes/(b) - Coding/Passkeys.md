2025-01-30 20:52
Status: 
Tags:

## References

Why Passkeys?
- Safer, Easier alternatives to passwords. Passkeys, users can sign into apps and websites with a biometric sensor (fingerprint or facial recognition), PIN, or pattern
- This removes the need for a password
	- Passwords, create security liability
- [[Multi-factor authentication]] requirements, replacing both a password and OTP
- Passkeys are standardised, single implementation enables a [[Passwordless]] experience across all of a users’ devices

**Convenience**
1. Users can select an account to sign in with. Typing the username is not required. 
2. Users can authenticate using device’s screen lock such as a fingerprint sensor, facial recognition or PIN
3. Once passkeys are created and registered, the user can switch to a new device and use it immediately without having to re-enroll


**Safer**
1. Developers only save public key to the server. → Far less value for a bad actor to hack into servers, and far less cleanup
2. Passkeys protect users from phising attacks. → The OS or the browser handles the verification
3. Passkeys reduce costs of sending SMS, making them safer and more cost-effective for 2FA

**Passkeys use [[public key]] cryptography!** Think about [[CS440]] where we learnt about Public and Private Keys. RSA technology. 

>[!question] How does the passkeys prevent remote attacks? Connect to each other locally?
No replay attacks. Each authentication session generates a unique, one-time cryptographic challenge that cannot be reused or replicated by an attacker

**The unique thing about passkeys** is that the private key does not leave the user’s phone. As always there is the registration process and then subsequently a authentication process. 

**Registration process**
Your device comes up with a public and private key. Private keys are stored on the device itself while public keys are sent to the server. Thus the server stores the public keys. This signifies the end of the registration process.

**Authentication Process**
The server will then send a challenge across to the Client and get the client to sign the challenge using the private key. Recall from [[CS440]] only the private key and the public keys can work to unlock each other. 

In this case, the server will receive the signed challenge back from the device. Decrypts it and then verify that the challenge is the same. Once it is the same, it will then grant access to the user.


