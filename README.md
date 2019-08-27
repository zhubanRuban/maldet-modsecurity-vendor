# Maldet Modsecurity Vendor

## Sources

12th paragraph [ MODSECURITY2 UPLOAD SCANNING ] of [maldetect README](https://www.rfxn.com/appdocs/README.maldetect)

[How to Create a ModSecurity Vendor](https://documentation.cpanel.net/display/CKB/How+to+Create+a+ModSecurity+Vendor)

## Installation

[Install a ModSecurity vendor in WHM](https://documentation.cpanel.net/display/ALD/ModSecurity+Vendors#ModSecurityVendors-InstallaModSecurityvendor)

# Custom Maldet ignore_inotify file

## Installation

```
wget -O /usr/local/maldetect/ignore_inotify https://github.com/zhubanRuban/maldet-modsecurity-vendor/raw/master/custom_ignore_inotify
service maldet restart
```

## Why

cPanel with MariaDB creates temp files with MAD and MAI extensions which are not covered by current rules:
```
^/var/tmp/#sql_.*\.MYD$
^/tmp/#sql_.*\.MYD$
```
so replaced with:
```
^/var/tmp/#sql_.*
^/tmp/#sql_.*
^/dev/shm/#sql_.*
```
