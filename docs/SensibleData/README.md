## Sensible data in views
- [ ] Disable screenshots in the activities/pages/layouts that shows sensitive data by setting a `FLAG_SECURE` to the layout.
- [ ] The app removes sensitive data from views when moved to the background.

## Sensitive data in logs
- [ ] Never log sensible data.
- [ ] Remove all useless logging-related sample of code in production release.

## Sensible data in responses
- [ ] Each HTTP Response from the backend must return only the minimum and essential required values.

## Sensitive data in 3rd parties
- [ ] Only allow necessary permissions in 3rd parties (jar, api calls, sdk, etc ...)
- [ ] Check used source code from 3rd parties (jar, api calls, sdk, etc ...)
- [ ] Check if 3rd parties are actively releasing new versions.
- [ ] Keep dependencies up to date at all time.


## Technical reference
- [ ] See the logging section : https://www.owasp.org/images/9/99/GiuseppePorcu-OWASPItalyDay19-10-2018.pdf

