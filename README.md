## Mobile security checklist (Android)

#### Data storage on device
- [ ] Protecting authentication tokens, private information, api keys or any other sensitive data.
- [ ] Keep out any sensible storage data on device if possible. (ex: get users permission with his jwt at each call instead of storing it on the device)
- [ ] Use KeyStore to encrypt sensitive data using keys provided by AndroidKeyStore. The app should use a public key to create a new private/public key pair for encrypting application secrets. And it can decrypt it with the private key. https://medium.com/@ericfu/securely-storing-secrets-in-an-android-application-501f030ae5a3 
- [ ] Protect access to KeyStore with user authentication on lock screen (PIN, password, fingerprint, ...) if the secure lock screen is disabled, the stored secrets becomes permanently invalid.
- [ ] Give a limited authorization time to the keys in the KeyStore (allowed only when screen lock is enabled, otherwise permanently remove access to keys)
- [ ] Validate that the clients device offers secure hardware backed keystore by validating KeyInfo.isInsideSecureHardware()
- [ ] Data validation when reading from the storage
- [ ] Data signature validation when reading from the storage (cryptographic controls such as HMAC to ensure data correctness)
- [ ] Data sanitization when reading from the storage
- [ ] Sensible data should not be stored in public shared preferences storage, it needs to be encrypted with the Android KeyStore first.
- [ ] Sensible data should not be stored in unencrypted database (SQLite, Realm, ...) storage
- [ ] Sensible data should not be stored in internal or external storage.

#### Sensitive data in logs
- [ ] Never log sensible data.
- [ ] Use tools like ProGuard to remove all logging-related code in production release.

#### Sensitive data in 3rd parties
- [ ] Only allow necessary/minimum permissions in AndroidManifest.xml for any 3rd parties (jar, api calls, sdk)
- [ ] Check used source code from 3rd parties (jar, api calls, sdk)
- [ ] Check if 3rd parties are actively releasing new versions
- [ ] Keep dependencies up to date at all time

#### Sensitive data in IPC
- [ ] Properly configure IPC to not leak sensitive data that content providers may allow app’s stored data to be accessed and modified by other apps.
- [ ] Identified by <provider> tag inside the AndroidManifest.xml
- [ ] android:exported should be explicitly set to “false” if the content is
meant to be accessible only by the app itself, otherwise define proper
read/write permissions inside the AndroidManifest.xml
- [ ] android:permission tags must be used to limit exposure to others inside the AndroidManifest.xml
- [ ] android:protectionLevel should be set to “signature” (content accessible only by apps signed with the same key) inside the AndroidManifest.xml

#### Sensible data in screenshots
- [ ] Explicitly disabled screenshots in the activities/pages/layouts that shows sensitive data by setting FLAG_SECURE to the layout.

#### Cryptographic API
- [ ] Do not create your own cryptographic algorithm
- [ ] Verify that the configuration of cryptographic algorithms used are aligned with best practices from NIST and BSI
- [ ] Do not use insecure java.util.Random for sensible data

#### Communication and networking
