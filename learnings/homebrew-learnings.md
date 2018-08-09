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
