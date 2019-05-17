rofl-ofdpa deps:
```
apt install autoconf libtool pkg-config linux-libc-dev libc6-dev libssl-dev libgoogle-glog-dev g++ libcunit1-dev libcppunit-dev
```
packaging deps
```
apt install build-essential devscripts debhelper dh-autorecon dh-autoreconf autogen
cd rofl-ofdpa
mkdir debian
dch --create -v 0.15-1 --package rofl-ofdpa
```
create debian/control
```
Source: rofl-ofdpa
Section: rofl-ofdpa
Priority: optional
Maintainer: Pierluigi Greto <pierluigi.greto@bisdn.de>

Package: rofl-ofdpa
Version: 0.15
Depends: rofl-common, autoconf, libtool, pkg-config, linux-libc-dev, libc6-dev, libssl-dev, libgoogle-glog-dev, g++, libcunit1-dev, libcppunit-dev
Architecture: any
Description: rofl-ofdpa
 When you need some sunshine, just run this
 small program!

```
create debian/rules:
```
#!/usr/bin/make -f
export DEB_BUILD_OPTIONS=nocheck

%:
        dh $@ --with autoreconf

```
to build
```
mv rofl-ofdpa rofl-ofdpa-0.15-1
tar -zcvf rofl-ofdpa_0.15.orig.tar.gz rofl-ofdpa-0.15-1
cd rofl-ofdpa-0.15-1/
debuild -us -uc
```
