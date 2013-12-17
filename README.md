## About

This script will:

 1. download the `Debian 7 "Wheezy"` server 64bit iso
 2. ... do some magic to turn it into a vagrant box file
 3. output `debian-wheezy-64.box`
 
Note:
GPG signed vagrant boxes produced by this script are available at http://basebox.libera.cc
 

## Requirements

 * Oracle VM VirtualBox
 * Vagrant
 * mkisofs
 * 7zip

## Usage on OSX

    ./build.sh

This should do everything you need. If you don't have `mkisofs` or `p7zip`, install [homebrew](http://mxcl.github.com/homebrew/), then:

    brew install cdrtools
    brew install p7zip

To add `debian-wheezy-64.box` with name `debian-7` into vagrant:

    vagrant box add "debian-7" debian-wheezy-64.box

## Usage on Linux

    ./build.sh

This should do everything you need. If you don't have `mkisofs` or `p7zip`:

    sudo apt-get install genisoimage
    sudo apt-get install p7zip-full

To add `debian-wheezy-64.box` with name `debian-7` into vagrant:

    vagrant box add "debian-7" debian-wheezy-64.box

### Notes

This script basted on original Carl's [repo](https://github.com/cal/vagrant-ubuntu-precise-64) and with some tweaks to be compatible Debian 7.1.
It was then forked from dotzero's [repo](https://github.com/dotzero/vagrant-debian-wheezy-64) to be more in line with debian best practises.

By **Vanilla** Debian install, we mean that we only install packages from the debian main archive and the strict minimum needed for vagrant and the provisioning tools (for details look at `d-i pkgsel/include` in the [preseed file](https://github.com/EmmanuelKasper/vagrant-debian-wheezy-64/blob/master/preseed.cfg#L60)).
