# To build
```
./autogen.sh
./configure
make
```

# To create the package
```
Commit the changes
cd pkg/testing/rpm
make
mock --dnf --resultdir=~/rpmbuild/RPMS/ --rebuild /home/pierluigi/Dev/basebox/rofl-ofdpa/pkg/testing/rpm/rofl-ofdpa-X-Y.gitcommit.fcZX.src.rpm
```
