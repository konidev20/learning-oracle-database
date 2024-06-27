# Installation of Oracle Database 19c on RHEL 8

## Dependencies
`compat-libcap-1` and `compat-libstdc++` dependencies are not available on RHEL 8.
```bash
# compat-libcap-1
dnf install -y http://mirror.centos.org/centos/7/os/x86_64/Packages/compat-libcap1-1.10-7.el7.x86_64.rpm
# compat-libstdc++
dnf install -y http://mirror.centos.org/centos/7/os/x86_64/Packages/compat-libstdc++-33-3.2.3-72.el7.x86_64.rpm
```
Install glibc and link `libnsl`
```bash
dnf install -y http://mirror.centos.org/centos/7/os/x86_64/Packages/glibc-2.17-317.el7.x86_64.rpm
ln -s /lib64/libnsl.so.2 /lib64/libnsl.so.1
```

# Guide
https://docs.oracle.com/en/database/oracle/oracle-database/19/ladbi/running-rpm-packages-to-install-oracle-database.html
