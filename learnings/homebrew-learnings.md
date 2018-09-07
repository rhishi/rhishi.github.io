# Homebrew Learnings

Homebrew is "the missing package manager for macOS".
Homebrew is at https://brew.sh/.

Installing Homebrew is copy-pasting and running one command mentioned prominently
on the home page.

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Things I have installed explicitly

```
# August 2018
brew install bash
brew install bash-completion
brew install git
brew install gdb
brew install node

# September 2018
brew install ipmitool
```

## Caveats

### gdb
gdb-8.1.1.high_sierra -- August 2018

* gdb requires special privileges to access Mach ports.
  You will need to codesign the binary. For instructions, see:
  https://sourceware.org/gdb/wiki/BuildingOnDarwin

* On 10.12 (Sierra) or later with SIP, you need to run this:<br>
  echo "set startup-with-shell off" >> ~/.gdbinit

### icu4c
icu4c-62.1.high_sierra -- August 2018

This formula is keg-only, which means it was not symlinked into /usr/local,
because macOS provides libicucore.dylib (but nothing else).

If you need to have this software first in your PATH run:
```
echo 'export PATH="/usr/local/opt/icu4c/bin:$PATH"' >> ~/.bash_profile
echo 'export PATH="/usr/local/opt/icu4c/sbin:$PATH"' >> ~/.bash_profile
```

For compilers to find this software you may need to set:
```
LDFLAGS:  -L/usr/local/opt/icu4c/lib
CPPFLAGS: -I/usr/local/opt/icu4c/include
```

### openssl
openssl-1.0.2p.high_sierra.bottle.tar.gz -- September 2018

A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
```
/usr/local/etc/openssl/certs
```

and run
```
/usr/local/opt/openssl/bin/c_rehash
```

openssl is keg-only, which means it was not symlinked into /usr/local,
because Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries.

If you need to have openssl first in your PATH run:
```
echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.bash_profile
```

For compilers to find openssl you may need to set:
```
export LDFLAGS="-L/usr/local/opt/openssl/lib"
export CPPFLAGS="-I/usr/local/opt/openssl/include"
```

## Install Example

Just to show you the beer mug emoji.  Oh, you don't see it?  Dang, character
encodings; Dang different fonts/systems rendering unicode/emoji differently.
```
==> Downloading https://homebrew.bintray.com/bottles/gdb-8.1.1.high_sierra.bottle.tar.gz
######################################################################## 100.0%
==> Pouring gdb-8.1.1.high_sierra.bottle.tar.gz
==> Caveats
gdb requires special privileges to access Mach ports.
You will need to codesign the binary. For instructions, see:
 
  https://sourceware.org/gdb/wiki/BuildingOnDarwin
 
On 10.12 (Sierra) or later with SIP, you need to run this:
 
  echo "set startup-with-shell off" >> ~/.gdbinit
==> Summary
🍺  /usr/local/Cellar/gdb/8.1.1: 53 files, 9.9MB
```
