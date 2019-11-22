# iac-dev - Release 3.0

This playbook configures RedHat/Centos workstation for `Infrastructure as Code` development with Ansible.

It configures your IaC Development workstation with:

- [Microsoft Visual Studio Code](https://code.visualstudio.com/)
- Git
- Ansible
- Docker CE +
  - Dockerfile and Makefile for Ansible testing/development
- Remote Desktop (xRDP+TigerVNC)

## Installation Instructions Centos 8 - 1905

  1. Download and install latest version of Centos 8 Build 1905 with Desktop Workstation [Centos Download](http://isoredirect.centos.org/centos/8/isos/x86_64/CentOS-8-x86_64-1905-dvd1.iso).
  2. During installation, create local user and grant administrator privileges
  3. After successful installation, open a terminal window:
  4. update packages: `sudo yum update` and reboot
  5. [Install Ansible](http://docs.ansible.com/) from pip:
     - `pip3 install ansible==2.9.1 --user`
  6. [Configure Git User](https://git-scm.com):
     - `git config --global user.email "you@example.com"`
     - `git config --global user.name "Your Name"`
  7. Clone this repository to your home directory: `git clone https://github.com/carlbuchmann/iac-dev`
  8. change directory to iac-dev `cd iac-dev/`
  9. Install requires roles: `ansible-galaxy install -r roles/requirements.yml --force`
  10. run playbook: `ansible-playbook iac-dev.yml --ask-become-pass`
  11. launch vscode: `code` and start developing!

### Recommended Visual Studio Code extentions

- [YAML Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Jinja](https://marketplace.visualstudio.com/items?itemName=samuelcolvin.jinjahtml)
- [PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [Ansible](https://marketplace.visualstudio.com/items?itemName=vscoss.vscode-ansible)
- [Excel Viewer](https://marketplace.visualstudio.com/items?itemName=GrapeCity.gc-excelviewer)
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

*Notes:*

- After installation, you may want to enable/disable extension depending on what you are doing, for example I disable GitLens unless I'm reviewing code.
- YAML Linting on Ansible playbook with *YAML Support by Red Hat* may report syntax problems which are false positives. It's not a problem with the extension but the schema, which is auto-generated from Ansible Code. see: [example issue](https://github.com/redhat-developer/vscode-yaml/issues/96)

## Getting Started with IaC

  1. [Getting Started with VSCode](https://code.visualstudio.com/docs)
  2. [Getting Started with Ansible](https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html)

## PRs welcome

Please submit a PR to help enhance this playbook!