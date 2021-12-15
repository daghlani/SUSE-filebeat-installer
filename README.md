# SLES Filebeat Installer

This repository in fact is an ansible project to install and config filebeat on suse 15 and 11. It is able to detect OS version and config it with specific init script. this different is because init script of filebeat is not compatible with suse 11 and so i had to change it.

### jenkins:
There is a jenkins file that you can set project to jenkins pipe and use it so easy,

## Usage

If you are familiar with ansible, you know ansible-playbooks. so to use this repository just you need write your `host-ips` in `hosts` file and then run installer.py whit below command:
```bash
ansible-playbook -i hosts installer.py
```

Or ifyou want to use this repository in jenkins, you can create a pipeline in jenkins and set this repo as source and  so on...
