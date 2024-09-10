**Just a simplified homebrew CA**

This script generates a CA certificate and key.
Then, from servers defined in the script headers, and after some sanity checks (like the server DNS resolves),
it generate certificate request and keys for servers, as defined in the header of the file.
It generates and, using the CA, signs these server's certificates based on those CSRs.
It creates PKCS12 format keystores (one with encrypted key and one withunencrypted key).
Finally it attempts to copy the certificates to said server using credentials specified in the script header.

```
declare -a servers=("test1" "test2")
DOMAIN=example.com
CAName="Example-CA"
UPLOADPATH="etc/"
REMOTEUSER=someuser
```
Change the variables in the header to something sensible.
