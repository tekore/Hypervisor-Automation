![standard-readme compliant](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white)

# Ubuntu Automation
Bare metal install of Ubuntu Server 24.04 with LXD via cloud-init

### Table of Contents
- [Prerequisites](#Prerequisites)
- [Usage](#usage)

### Prerequisites
- You have physical access to the server and two USB drives of at least 8GB in size.

### ISO Download
```sh
https://ubuntu.com/download/server/thank-you?version=24.04&architecture=amd64&lts=true
```

### Usage
- Create a bootable Ubuntu-server USB and another USB called 'CIDATA'
- Customise the file 'user-data' and copy it to the 'CIDATA' USB
- Boot the server (with both USBs plugged in), from the Ubuntu installer USB and type 'yes' when the autoinstall prompt shows