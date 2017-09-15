# Nginx with [ldap] and [naxsi] modules for custom compilation

* Nginx version: 1.11.0
* Tested build env: Centos 7 (7.4.1708) 64-bit

## Download
```sh
git clone https://github.com/garther/nginx-naxsi-ldap.git
mv nginx-naxsi-ldap/rpmbuild ~/
```

## Compilation

### Install prereqs:
This group has everything is needed to start building RPM from source.
```sh
yum groupinstall --enablerepo=epel  'Development Tools'
```
### Install dependecies
```sh
cd ~/rpmbuild
yum-builddep SPECS/nginx.spec
```
## Build
```sh
cd ~/rpmbuild
rpmbuild -bb nginx-naxsi-ldap/rpmbuild/SPECS/nginx.spec
```
## Install
The RPMSs are created in ~/rpmbuild/RPMS/x86_64/ directory. You can install them locally or move to another host.
```sh
cd ~/rpmbuild/RPMS/x86_64/
yum install nginx-1.11.0-1.el7.centos.ngx.x86_64.rpm
```
   [naxsi]: <https://github.com/nbs-system/naxsi>
   [ldap]: <https://github.com/kvspb/nginx-auth-ldap>

