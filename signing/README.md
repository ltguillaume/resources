# New signing procedure (with .asc file)

My releases have corresponding `*.sha256` checksum files and `*.asc` signature files. You can use [gpg (GnuPG)](https://gnupg.org) to verify that the builds haven't been tampered with by the server or while in transit.

#### First time only:
1. Download my public key [ltguillaume-signing.key](ltguillaume-signing.key)  
    The public key's fingerprint is `2D4A31E7F5DA47ECA08E9668F965AFD64E967D2A`
2. Import the key:
    ```
    gpg --import ltguillaume-signing.key
    ```

#### Verify the build:
1. Download the release's `[Program-Name_x.x.x].zip` and `[Program-Name_x.x.x].zip.asc` files
2. Verify the zip file:
    ```
    gpg --verify [Program-Name_x.x.x].zip.asc
    ```


# Old procedure (with .sig file)

My releases have corresponding `*.sha256` checksum files, which are then signed with `*.sha256.sig` files. You can use [gpg (GnuPG)](https://gnupg.org) to verify that the builds haven't been tampered with by the server or while in transit.

#### First time only:
1. Download my public key [ltguillaume-signing.key](ltguillaume-signing.key)  
    The public key's fingerprint is `2D4A31E7F5DA47ECA08E9668F965AFD64E967D2A`
2. Import the key:
    ```
    gpg --import ltguillaume-signing.key
    ```

#### Verify the build:
1. Download the release's `[Program-Name_x.x.x].zip`, `[Program-Name_x.x.x].sha256` and `[Program-Name_x.x.x].sha256.sig` files
2. Verify the hash file and check the .zip's hash:
    ```
    gpg --verify [Program-Name_x.x.x].sha256.sig
    sha256sum -c [Program-Name_x.x.x].sha256
    ```