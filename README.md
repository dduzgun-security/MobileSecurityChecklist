## Mobile security checklist

#### Data storage on device (Android)
- [ ] Protecting authentication tokens, private information, api keys or any other sensitive data.
- [ ] Keep out any sensible storage data on device if possible. (ex: get users permission with his jwt at each call instead of storing it on the device)
- [ ] Use KeyStore to encrypt sensitive data using keys provided by AndroidKeyStore. The app should use a public key to create a new private/public key pair for encrypting application secrets. And it can decrypt it with the private key. https://medium.com/@ericfu/securely-storing-secrets-in-an-android-application-501f030ae5a3 
- [ ] Protect access to KeyStore with user authentication on lock screen (PIN, password, fingerprint, ...) if the secure lock screen is disabled, the stored secrets becomes permanently invalid.
- [ ] Give a limited authorization time to the keys in the KeyStore (allowed only when screen lock is enabled, otherwise permanently remove access to keys)
- [ ] Data validation when reading from the storage
- [ ] Data signature validation when reading from the storage (cryptographic controls such as HMAC to ensure data correctness)
- [ ] Data sanitization when reading from the storage
- [ ] Sensible data should not be stored in public shared preferences storage, it needs to be encrypted with the Android KeyStore first.
- [ ] Sensible data should not be stored in unencrypted database (SQLite, Realm, ...) storage
- [ ] Sensible data should not be stored in internal or external storage.
