![standard-readme compliant](https://img.shields.io/badge/VMware-231f20?style=for-the-badge&logo=VMware&logoColor=white)
# Hypervisor Automation

Bare metal install of ESXI and VCenter as automated as possible.

## Table of Contents
- [Goals](#Goals)
- [Prerequisites](#Prerequisites)
- [Usage](#usage)
- [Issues](#Issues)
- [Maintainers](#maintainers)

## Goals
The goals for this repository are:

1. Automate the install and configuration of ESXI and VCenter on home infrestructure so Terraform can be ran against it.
2. Continually improve the current solution to minimise the need for human intervention.

## Prerequisites
- You have physical access to the server and a USB of atleast 8GB.

## ISO Downloads
VCenter ISO:
```sh
https://customerconnect.vmware.com/downloads/get-download?downloadGroup=VC800
```
ESXI ISO:
```sh
https://customerconnect.vmware.com/en/evalcenter?p=free-esxi8
```

## Usage

### ESXI
- Fill out the file 'ks.cfg'
- Create a bootable USB using the ESXI ISO above.
- Copy the files 'boot.cfg' and 'ks.cfg' files onto the ESXI installer USB in the directory '/efi/boot/'.
- Boot the server from the ESXI installer USB and wait for the install to complete.

### VCenter
- Fill out the file 'VCenter_template.json'
- Mount the VCenter ISO ('VMware-VCSA-all-....iso') and cd into it's directory /vcsa-cli-installer/lin64/

- Run the install
```sh
./vcsa-deploy install <TEMPLATE-PATH>/VCenter_template.json --accept-eula --no-ssl-certificate-verification --acknowledge-ceip
```

## Issues

## Maintainers
[@Tekore](https://github.com/tekore)
