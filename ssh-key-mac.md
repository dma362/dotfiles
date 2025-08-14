# SSH Key Setup on Mac

## Check for existing SSH keys
```bash
ls -al ~/.ssh
```

## Generate new SSH key
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Press enter to save the key to the default location.

## Add SSH key to ssh-agent
Start ssh-agent in the background:
```bash
eval "$(ssh-agent -s)"
```

First, check if you already have an ssh config file:
```bash
open ~/.ssh/config
```

If not, create it:
```bash
touch ~/.ssh/config
```

Then open it in a text editor and add the following contents:
```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```
Note: if you didn't use a passphrase, omit the `UseKeychain` line

## Add private key to ssh-agent and store passphrase in keychain
```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

## Copying contents of public key (to add to e.g. Github)
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```
