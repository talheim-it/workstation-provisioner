# workstation-provisioner
Provisioning script for local workstation

Tested with
 - Fedora 32 Workstation

## Ansible command
ansible-playbook playbook/workstation.yml --ask-become-pass

## Vars
```
download_dir: /home/example/Data/wks_downloads
packer_version: 1.6.1
vagrant_version: 2.2.9
terraform_version: 0.13.0
vault_version: 1.5.0
```

## Example playbook
```
- hosts: 127.0.0.1
  connection: local
  roles:
     - workstation-tools
  vars: 
     download_dir: /home/titrumbold/Data/wks_downloads
     packer_version: 1.6.1
     vagrant_version: 2.2.9
     terraform_version: 0.13.0
     vault_version: 1.5.0
     flatpaks:
       - com.visualstudio.code
       - io.atom.Atom
       - org.signal.Signal
       - org.telegram.desktop
       - org.videolan.VLC
       - chat.rocket.RocketChat
       - com.anydesk.Anydesk
       - com.bitwarden.desktop
       - org.mozilla.firefox
       - org.remmina.Remmina
       - org.jitsi.jitsi-meet
     virtualbox_url: https://download.virtualbox.org/virtualbox/6.1.12/VirtualBox-6.1.12-139181-Linux_amd64.run  
```