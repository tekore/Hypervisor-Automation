![standard-readme compliant](https://img.shields.io/badge/VMware-231f20?style=for-the-badge&logo=VMware&logoColor=white)

# VSphere Automation
Bare metal install of ESXI and VCenter as automated as possible.

## Table of Contents
- [Prerequisites](#Prerequisites)
- [Usage](#usage)
- [Issues](#Issues)

## Prerequisites
- You have physical access to the server and a USB of at least 8GB.
- You have a seperate PC with network access to the server to run the 'VCenter' steps.

## ISO Downloads
```sh
https://customerconnect.vmware.com/evalcenter?p=vsphere-eval-8
```
##### Note: You will need to create an account and login for the above link to allow you to download the required ISOs.

## Usage
### ESXI
- Fill out the file 'ks.cfg'.
- Create a bootable USB using the ESXI ISO above.
- Copy the files 'boot.cfg' and 'ks.cfg' files onto the ESXI installer USB in the directory '/efi/boot/'.
- Boot the server from the ESXI installer USB and wait for the install to complete.

### VCenter
- Fill out the file 'VCenter_template.json'.
- Mount the VCenter ISO ('VMware-VCSA-all-....iso') and cd into it's directory '/vcsa-cli-installer/lin64/'.
- Run the install.

```sh
./vcsa-deploy install <TEMPLATE-PATH>/VCenter_template.json --accept-eula --no-ssl-certificate-verification --acknowledge-ceip
```

## Issues
- The ESXI ks.cfg file will only set a single USB ethernet device as the management network. 
```sh
network --bootproto=static --device=vusb0 --ip=<IP_ADDRESS> 
```
This will need to be changed to ensure compatibility on differing infrastructure.
