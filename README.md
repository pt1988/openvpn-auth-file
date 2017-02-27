# openvpn-auth-file

## Purpose

Sometimes username and password authentication is needed when connecting to openvpn server. There are plenty of plugins written in python, php, ruby, ... Nevertheless, this one is written perl and uses htpasswd format file as a database.

## Dependencies

Only perl and libapache-htpasswd-perl are required.

## How to use

1. Copy the script somewhere (I personally suggest /usr/lib/openvpn).
2. Update your openvpn config
```
auth-user-pass-verify "/usr/lib/openvpn/openvpn-auth-file.pl /etc/openvpn/passwd" via-env
script-security 3
client-cert-not-required
username-as-common-name
```
3. Generate your username and password (you can use this site http://www.htaccesstools.com/htpasswd-generator/) and put it to /etc/openvpn/passwd
4. Restart openvpn

## CentOS

```
yum install perl-Apache-Htpasswd
yum install perl-Crypt-PasswdMD5
```

## Testing

This script has been tested on currently stable Debian (wheezy).
