## From Zero to Encyrpted Secrets in 2 Minutes with SOPS and GPG

Accompanying repository for the blog post: [https:///ervinbarta.com/2020/12/05/from-zero-to-encrypted-secrets-in-5-minutes](https:///ervinbarta.com/2020/12/05/from-zero-to-encrypted-secrets-in-2-minutes)

```sh
# Clone the example repository
$ git clone https://github.com/ervinb/sops-gpg-example.git
$ cd sops-gpg-example

# Import the encryption key
## The path is Keybase specific and it will work on any platform - no need to use your local filesystem path
$ gpg --import <(keybase fs read /keybase/team/sopsgpgexample/pgp/key.asc)
## Or if you don't have Keybase set up yet
$ gpg --import <(curl -L https://gist.githubusercontent.com/ervinb/288c44a45cf2614a0684bea333b3aa36/raw/sops-gpg-example.asc)

# Decrypt and open the file
$ sops secrets/mysecrets.dev.enc.yaml
```
