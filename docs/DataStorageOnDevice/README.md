## Data storage on device
- [ ] System credential storage facilities need to be used to store sensitive data, such as PII, user credentials or cryptographic keys.
- [ ] No sensitive data should be stored outside of the app container or system credential storage facilities.
- [ ] When possible, no sensitive data should be stored locally on the mobile device. Instead, data should be retrieved from a remote endpoint when needed and only be kept in memory. (ex: get users permission with his jwt at each http request call instead of storing it on the device since his permissions may change anytime)
- [ ] If sensitive data is still required to be stored locally, it should be encrypted using a key derived from hardware backed storage (such as KeyStore) which requires authentication.
- [ ] The app should request only the minimum number of permissions necessary to function properly. When possible, the app should relinquish some of these permissions when they're no longer needed.
- [ ] The app’s local storage should be wiped after an excessive number of failed authentication attempts.
- [ ] The app does not hold sensitive data in memory longer than necessary, and memory is cleared explicitly after use.
- [ ] No sensitive data should be written to application logs.
- [ ] No sensitive data is included in backups generated by the mobile operating system.
- [ ] Ensure data validation (for content and signature with cryptographic controls such as HMAC to ensure data correctness) and sanitization when reading from the storage
- [ ] Sensible data should not be stored in public shared preferences storage, it needs to be encrypted first and in private mode.
- [ ] Sensible data should not be stored in unencrypted database (SQLite, Realm, ...) storage
- [ ] Sensible data should not be stored in internal or external storage.

## Technical reference (Android)
- [ ] Secure data storage on Android reference: https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05d-Testing-Data-Storage.md
- [ ] Secure data storage on Android reference: https://developer.android.com/topic/security/best-practices
- [ ] Permissions : https://developer.android.com/topic/security/best-practices#permissions
- [ ] Possible implementation solution (POC): https://medium.com/@ericfu/securely-storing-secrets-in-an-android-application-501f030ae5a3

## Technical reference (IOS)
- [ ] Secure data storage on IOS reference: https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06d-Testing-Data-Storage.md
- [ ] Secure data storage on IOS reference: https://mobile-security.gitbook.io/mobile-security-testing-guide/ios-testing-guide/0x06d-testing-data-storage#checking-logs-for-sensitive-data-mstg-storage-3
