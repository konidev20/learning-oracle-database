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

# Post-Installation
## Set Oracle Home and Oracle SID
Create a file called `set-env.sh`. This will set the environment variable in the `.bashrc` file. You can run this on all the users that need access to Oracle Database. Replace `<SID>` with your instance ID.
```bash
echo '' >> $HOME/.bashrc; echo '#Oracle Environment Variables' >> $HOME/.bashrc
echo 'export PATH="/opt/oracle/product/19c/dbhome_1/bin:$PATH"' >> $HOME/.bashrc
echo 'export ORACLE_SID=<SID>' >> $HOME/.bashrc
echo 'export ORACLE_HOME="/opt/oracle/product/19c/dbhome_1"' >> $HOME/.bashrc
```
Run `source .bashrc` after this.
