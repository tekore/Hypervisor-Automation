![standard-readme compliant](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white)

# Ubuntu Automation
Bare metal install of Ubuntu Server 24.04 via cloud-init

## Table of Contents
- [Prerequisites](#Prerequisites)
- [Usage](#usage)

## Prerequisites
- You have physical access to the server and two USB drives of at least 8GB.

## ISO Downloads
```sh
https://ubuntu.com/download/server/thank-you?version=24.04&architecture=amd64&lts=true
```

## Usage
- Create a bootable Ubuntu-server USB and another USB called 'CIDATA'
- Custom the file 'user-data' to fit your personal install (use mine as an example)
- Boot the server from the Ubuntu installer USB and type 'yes' when the cloud-init prompt shows
