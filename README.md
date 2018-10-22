# iac-dev - Release 2.1

This playbook configures RedHat/Centos or Debian/Ubuntu workstation for `Infrastructure as Code` development with Ansible.

It configures your IaC Development workstation with:

- [Microsoft Visual Studio Code](https://code.visualstudio.com/)
- Python
- PowerShell Core for Linux
- Latest Version of Git
- Latest Version of Ansible +
  - WinRM + Kerberos Authentication for windows automation through Ansible
  - Various python libraries for common modules (Azure,AWS,Google Cloud,F5,NAPALM, or add your own!)
- Remote Desktop (xRDP+TigerVNC) for easy access (RedHat/Centos Only)

## Installation Instructions RedHat/Centos

  1. Download and install latest version of Centos/RedHat 7 with Gnome Desktop Environment [Centos Download](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Everything-1804.iso).
  2. During installation, create local user and grant administrator privileges
  3. After successful installation, open a terminal window:
  4. [Install Ansible](http://docs.ansible.com/intro_installation.html): `sudo yum install ansible`.
  5. [Install Git](https://git-scm.com/download/linux) and configure Git user: 
     - `sudo yum install git`
     - `git config --global user.email "you@example.com"`
     - `git config --global user.name "Your Name"`
  6. Clone this repository to your home directory: `git clone https://github.com/carlbuchmann/iac-dev`
  7. *Optional Customization* :
     - to enable WinRM: Edit `./iac-dev/roles/ansible-engine/defaults/main.yml` and enter your active directory domain information
     - Add/remove vscode extensions: Edit `./iac-dev/roles/vscode/defaults/main.yml` ( recommended extensions will be installed by default )
  8. run playbook: `ansible-playbook iac-dev.yml --ask-become-pass`
  9. launch vscode: `code` and start developing!


## Installation Instructions Debian/Ubuntu

  1. Download and install latest version of Debian/Ubuntu 18.0.4 Desktop [Ubuntu Download](https://www.ubuntu.com/download/desktop).
  2. During installation, create local user and grant administrator privileges
  3. After successful installation, open a terminal window:
  4. [Install Ansible](http://docs.ansible.com/intro_installation.html): 
     - `sudo apt-add-repository ppa:ansible/ansible`
     - `sudo apt-get update`
     - `sudo apt-get install ansible`.
  5. [Install Git](https://git-scm.com/download/linux) and configure Git user:
     - `sudo apt-get install git-core`
     - `git config --global user.email "you@example.com"`
     - `git config --global user.name "Your Name"`
  6. Clone this repository to your home directory: `git clone https://github.com/carlbuchmann/iac-dev`
  7. *Optional Customization* :
     - to enable WinRM: Edit `./iac-dev/roles/ansible-engine/defaults/main.yml` and enter your active directory domain information
     - Add/remove vscode extensions: Edit `./iac-dev/roles/vscode/defaults/main.yml` ( recommended extensions will be installed by default )
  8. run playbook: `ansible-playbook iac-dev.yml --ask-become-pass`
  9.  launch vscode: `code` and start developing!


#### Recommended Visual Studio Code extentions

- [YAML Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Jinja](https://marketplace.visualstudio.com/items?itemName=wholroyd.jinja)
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
