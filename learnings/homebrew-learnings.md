# Homebrew Learnings

Homebrew is "the missing package manager for macOS".
Homebrew is at https://brew.sh/.

Installing Homebrew is copy-pasting and running one command mentioned prominently
on the home page.

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
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
