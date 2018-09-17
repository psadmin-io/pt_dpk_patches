This repository contains fixes and enhancements to Oracle's PeopleSoft DPK.

## Pre-Requisites

### Windows
1. puppet-agent - [5.5.6+](http://downloads.puppetlabs.com/windows/puppet/)
2. puppet module - [acl](https://forge.puppet.com/puppetlabs/acl)
 `puppet module install puppetlabs-acl --version 2.0.1`
3. puppet module - [inifile](https://forge.puppet.com/puppetlabs/inifile)
`puppet module install puppetlabs-inifile --version 2.3.0`
4. puppet module - [registry](https://forge.puppet.com/puppetlabs/registry)
`puppet module install puppetlabs-registry --version 2.0.2`
5. puppet module - [xml_fragment](https://forge.puppet.com/ianoberst/xml_fragment)
`puppet module install ianoberst-xml_fragment --version 1.0.2`  
6. Set `JAVA_HOME` in system environment variables.
7. If using custom service accounts, each service account must be granted rights to logon as service or the service will fail to start.

Optional 
* [DeepRemove2](https://github.com/juanpablojofre/deepremove) - Supports removing windows folders that are too deep to remove with traditional tools or shell commands.

## How to apply DPK patch
1. Copy pt_dpk_[version].patch to `/pt/dpk/puppet/production/modules/`
2. Navigate to `/pt/dpk/puppet/production/modules/`
3. Run `git apply pt_dpk_[version].patch`
For example, if applying DPK 8.56.10 patch, you would run the following command  
`git apply pt_dpk_85610.patch`