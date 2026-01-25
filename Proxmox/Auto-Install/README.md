## Proxmox Auto Install

## Contents
- [Prerequisites](##Prerequisits)

## Prerequisites
- You have a USB drive
- A Linux host you can use to create the bootable USB (Commands may vary slightly if you're not using Ubuntu 24.04)

## How-To
1. Add the repo and GPG key for the 'proxmox-auto-install-assistant' tool and update the package list
```sh
echo "deb [arch=amd64] http://download.proxmox.com/debian/pve bookworm pve-no-subscription" > /etc/apt/sources.list.d/pve-install-repo.list
wget https://enterprise.proxmox.com/debian/proxmox-release-bookworm.gpg -O /etc/apt/trusted.gpg.d/proxmox-release-bookworm.gpg
apt update
```

2. Install the package 'proxmox-auto-install-assistant'
```sh
sudo apt install proxmox-auto-install-assistant -y 
```

3. Customise the answer.toml file values (Change the url unless you want to use my script)
[answer.toml](https://github.com/tekore/HomeOps/blob/main/Auto-Install/answer.toml)

4. Customise the variables in the first-boot-script.sh file
[first-boot-script.sh](https://github.com/tekore/HomeOps/blob/main/Auto-Install/first-boot-script.sh)
##### Create a GitHub personal access token here --> [GitHub_PAT](https://github.com/settings/personal-access-tokens) ###### Note: Ensure the token has Read/Write permissions for 'Actions' and 'Administration'
5. Validate your answer.toml file
```sh
proxmox-auto-install-assistant validate-answer answer.toml
```

6. Download the Proxmox-VE_8 ISO
[Proxmox_Download](https://enterprise.proxmox.com/iso/proxmox-ve_8.4-1.iso)

7. Build your custom ISO
```sh
proxmox-auto-install-assistant prepare-iso ./proxmox-ve_*.iso --fetch-from iso --answer-file ./answer.toml --on-first-boot ./first-boot-script.sh
```

8. Now burn the newly created ISO image to a USB (using a tool such as 'balenaEtcher')
[balenaEtcher_Download](https://etcher.balena.io/#download-etcher)