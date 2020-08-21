# workstation-provisioner
Provisioning script for local workstation

Tested with
 - Fedora 32 Workstation

## Ansible command
ansible-playbook playbook/workstation.yml --ask-become-pass

## Vars
```
username: username
shell: /usr/bin/zsh
download_dir: /home/username/Data/wks_downloads
packer_version: 1.6.1
vagrant_version: 2.2.9
terraform_version: 0.13.0
vault_version: 1.5.0
consul_version: 1.8.3
nomad_version: 0.12.3
virtualbox_url: https://download.virtualbox.org/virtualbox/6.1.12/VirtualBox-6.1.12-139181-Linux_amd64.run
```

## Example playbook
```
- hosts: 127.0.0.1
  connection: local
  roles:
     - workstation-tools
  vars:
     username: username
     shell: /usr/bin/zsh 
     download_dir: /home/username/Data/wks_downloads
     packer_version: 1.6.1
     vagrant_version: 2.2.9
     terraform_version: 0.13.0
     vault_version: 1.5.0
     consul_version: 1.8.3
     nomad_version: 0.12.3
     packages:
       - wget
       - curl
       - zsh
       - git
       - vim 
       - gem
       - powerline
       - vim-powerline
       - tmux-powerline
       - powerline-fonts
       - powershell-7.0.3-1.rhel.7.x86_64
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
       - com.microsoft.Teams
     virtualbox_url: https://download.virtualbox.org/virtualbox/6.1.12/VirtualBox-6.1.12-139181-Linux_amd64.run
```
