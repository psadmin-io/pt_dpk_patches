
This repository contains fixes and enhancements to Oracle's PeopleSoft DPK.

## Pre-Requisites

### Windows
1. puppet-agent - [5.5.6+](http://downloads.puppetlabs.com/windows/puppet/)  
2. puppet module - [acl](https://forge.puppet.com/puppetlabs/acl)  
 `puppet module install puppetlabs-acl --version 2.0.1 --confdir [dir]`
3. puppet module - [inifile](https://forge.puppet.com/puppetlabs/inifile)  
`puppet module install puppetlabs-inifile --version 2.3.0 --confdir [dir]`
4. puppet module - [registry](https://forge.puppet.com/puppetlabs/registry)  
`puppet module install puppetlabs-registry --version 2.0.2 --confdir [dir]`
5. puppet module - [xml_fragment](https://forge.puppet.com/ianoberst/xml_fragment)  
`puppet module install ianoberst-xml_fragment --version 1.0.2 --confdir [dir]`
6. puppet module - [stdlib 4.11+](https://forge.puppet.com/puppetlabs/stdlib)  
`puppet module upgrade puppetlabs-stdlib --confdir [dir]`
7. Set `JAVA_HOME` in system environment variables.
8. If using custom service accounts, each service account must be granted rights to logon as service or the service will fail to start.

## Features  

### Customization Enhancements
* Windows service customization for app/prcs/pia domains.
* Registry support for domain services.
* PIA XML/Property file support for modifications.
* Custom file support to copy files to app/prcs/pia domain folders post-installation.

### Bug Fixes
* Fixes WebLogic patch support for windows.
* Fixes Tuxedo patch support for windows.
* Fixes various Tuxedo install/uninstall issues.
* Fixes various WebLogic install/uninstall issues.
* Fixes Process Scheduler feature validation (change `KIOSK` to `PPM`)
* Other minor cleanup/fixes.

## How to apply DPK patch
1. Copy pt_dpk_[version].patch to `/pt/dpk/puppet/production/modules/`
1. Navigate to `/pt/dpk/puppet/production/modules/`
1. On Windows platform, set `git config core.autocrlf input`
1. Run `git apply pt_dpk_[version].patch`  
For example, if applying DPK 8.56.10 patch, you would run the following command  
`git apply -v pt_dpk_85610.patch`