![](./penguins-repos.png)
# [penguins-repos](https://pieroproietti.github.io/penguins-repos/)

This repository hosts the official packages for penguins-eggs for various Linux distributions. All packages and repository metadata are signed.

## Quick Navigation

* Debian / Ubuntu
* Fedora 42
* Enterprise Linux 9 (EL9)
* openSUSE Leap
* Arch Linux
* Manjaro
* Alpine Linux

## Debian, Ubuntu, and other derivatives.

#### Add the GPG key
```
#    (You must first download the public GPG key and place it in /etc/apt/keyrings/)
sudo wget -O /etc/apt/keyrings/penguins-eggs.gpg [https://pieroproietti.github.io/penguins-repos/KEY.asc](https://pieroproietti.github.io/penguins-repos/KEY.asc)
```
#### Add the repository source
```
echo "deb [signed-by=/etc/apt/keyrings/penguins-eggs.gpg] [https://pieroproietti.github.io/penguins-repos/deb](https://pieroproietti.github.io/penguins-repos/deb) stable main" | sudo tee /etc/apt/sources.list.d/penguins-eggs.list
```

#### Update and install
```
sudo apt-get update
sudo apt-get install penguins-eggs
```

## Fedora 42

#### Add the repository definition
```
sudo tee /etc/yum.repos.d/penguins-eggs.repo > /dev/null <<'EOF'
[penguins-eggs]
name=penguins-eggs Repository
baseurl=[https://pieroproietti.github.io/penguins-repos/rpm/fedora/42](https://pieroproietti.github.io/penguins-repos/rpm/fedora/42)
enabled=1
gpgcheck=1
gpgkey=[TODO: Add the URL to your GPG public key here]
EOF
```
#### Install the package
```
sudo dnf install penguins-eggs
```

# RHEL, AlmaLinux, Rocky Linux

#### Add the repository definition
```
sudo tee /etc/yum.repos.d/penguins-eggs.repo > /dev/null <<'EOF'
[penguins-eggs]
name=penguins-eggs Repository
baseurl=[https://pieroproietti.github.io/penguins-repos/rpm/el/9](https://pieroproietti.github.io/penguins-repos/rpm/el/9)
enabled=1
gpgcheck=1
gpgkey=[TODO: Add the URL to your GPG public key here]
EOF
```
#### Install the package
```
sudo dnf install penguins-eggs
```

## openSUSE Leap

#### Add the repository (it will prompt to import the GPG key)
```
sudo zypper addrepo -g -f '[https://pieroproietti.github.io/penguins-repos/rpm/opensuse/leap](https://pieroproietti.github.io/penguins-repos/rpm/opensuse/leap)' penguins-eggs
```
#### Refresh and install
```
sudo zypper refresh
sudo zypper install penguins-eggs
```

## Arch Linux

#### Add the following lines to the end of /etc/pacman.conf
```
[penguins-eggs]
SigLevel = Required DatabaseOptional
Server = [https://pieroproietti.github.io/penguins-repos/arch](https://pieroproietti.github.io/penguins-repos/arch)
```
#### Import and sign the GPG key
```
#    You must retrieve and locally sign the GPG key used by the repository.
# [TODO: Add your GPG Key ID here]
#
# EXAMPLE:
# sudo pacman-key --recv-key <YOUR_GPG_KEY_ID>
# sudo pacman-key --lsign-key <YOUR_GPG_KEY_ID>
```
#### Update and install
```
sudo pacman -Syu
sudo pacman -S penguins-eggs
```

## Manjaro (same as Arch, different URL)

#### Add the following lines to the end of /etc/pacman.conf
```
[penguins-eggs]
SigLevel = Required DatabaseOptional
Server = [https://pieroproietti.github.io/penguins-repos/manjaro](https://pieroproietti.github.io/penguins-repos/manjaro)
```
#### Import and sign the GPG key
```
#    You must retrieve and locally sign the GPG key used by the repository.
# [TODO: Add your GPG Key ID here]
#
# EXAMPLE:
# sudo pacman-key --recv-key <YOUR_GPG_KEY_ID>
# sudo pacman-key --lsign-key <YOUR_GPG_KEY_ID>
```

#### Update and install
```
sudo pacman -Syu
sudo pacman -S penguins-eggs
```

## Alpine Linux

#### Add the public GPG key

```
#    (The key filename must match the one in the repo)
sudo wget -O /etc/apk/keys/piero.proietti@gmail.com-68452915.rsa.pub [https://pieroproietti.github.io/penguins-repos/alpine/piero.proietti@gmail.com-68452915.rsa.pub](https://pieroproietti.github.io/penguins-repos/alpine/piero.proietti@gmail.com-68452915.rsa.pub)
```
#### Add the repository to /etc/apk/repositories
```
echo "[https://pieroproietti.github.io/penguins-repos/alpine/x86_64/packaging/x86_64](https://pieroproietti.github.io/penguins-repos/alpine/x86_64/packaging/x86_64)" | sudo tee -a /etc/apk/repositories
```
#### Update and install
```
sudo apk update
sudo apk add penguins-eggs
```

# Source Project

penguins-eggs is developed by Piero Proietti. For source code, documentation, and issue tracking, please visit the main project repository:

github.com/pieroproietti/penguins-eggs
