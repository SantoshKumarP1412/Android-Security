# Key store and Key signing:  

The Android Keystore and key signing are essential components in ensuring the security and integrity of Android applications.

The Android Keystore System allows developers to securely store cryptographic keys in a way that makes them less susceptible to extraction and misuse.

Common Operations
* Generating Keys: You can generate asymmetric (RSA, EC) and symmetric (AES) keys.
* Using Keys: Keys can be used for various operations like encryption, decryption, signing, and verification.
* Storing and Retrieving Keys: Once generated, keys can be stored and later retrieved for cryptographic operations.

Key Generation:

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/763b2169-4fd8-4ce8-adb3-c3b52f864f21)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/155fa0a1-150c-422e-a821-0b0918dff0f3)

> keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000

Key signing is a crucial process in Android development that ensures the authenticity and integrity of an APK file. Each APK must be signed with a certificate before it can be installed on a device.

Key Components
* Signing Keys: The private key used to sign the APK, which must be kept secure.
* Certificates: The public key certificate corresponding to the signing key, embedded in the APK, allows users to verify the source of the application.
Tools Used:


APK Signature Scheme v2 and v3

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/86552657-0a55-4f14-bff8-ac071b6b03af)


Enhances security by providing stronger guarantees that the APK hasn't been tampered with.
The newer Android versions (7.0 and above) use APK Signature Scheme v2 or v3, which offers additional protections compared to the original JAR signing.

Jarsigner:
Jarsigner can sign JAR files (which APKs are a type of) with a private key from a keystore.
It can also verify the signatures of signed JAR files, ensuring that the content hasn't been tampered with.
 Used to sign Java ARchive (JAR) files, including APKs.
Signs the APK file using the private key from the keystore

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/2de6eaca-a538-46b8-ad09-c478512b8c7c)
