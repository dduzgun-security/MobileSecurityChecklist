 ## Secure communication
 - [ ] Use SSL trafic everywhere
 - [ ] Implement a network security configuration to configure trusted CA
 - [ ] Check for certificate expiration
 - [ ] Use certificate pinning to associate a host with their expected X509 certificate or public key.
 - [ ] Use implicit intents and non-exported content providers
 - [ ] Show an app chooser to allow user sto transfer sensible information only to trusted apps.
  - [ ] Apply signature-based permissions
  - [ ] Disallow access to the app's content providers if there are no intents to send data to other apps
  - [ ] Ask for credentials before showing sensitive information
  - [ ] Ensure that no HTTP Requests containing sensible information in the URL are passed around.

  ## Technical reference (Android)
  - [ ] For Android : https://developer.android.com/training/articles/security-ssl
  - [ ] For Android : https://developer.android.com/training/articles/security-config#manifest

  ## Technical reference (IOS)
- [ ] For IOS : https://developer.apple.com/documentation/security/secure_transport