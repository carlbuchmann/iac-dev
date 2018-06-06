# iac-dev - Release 0.1

This playbook configures centos/redhat workstation for `Infrastructure as Code` development with Ansible.

It configures your IaC Development workstation with:

- Remote Desktop (xRDP+TigerVNC) for easy access
- [Microsoft Visual Studio Code](https://code.visualstudio.com/)
- Latest Version of Git
- Latest Version of Ansible +
  - WinRM + Kerberos Authentication for windows automation through Ansible
  - Various python libraries for common modules (Azure,AWS,F5,NAPALM, or add your own!)

## Installation Instructions

  1. Download and install latest version of Centos/RedHat 7 with Gnome Desktop Environment [Centos Download](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Everything-1804.iso).
  2. [Install Ansible](http://docs.ansible.com/intro_installation.html): `sudo yum install ansible`.
  3. [Install Git](https://git-scm.com/download/linux): `sudo yum install git`
  4. Clone this repository to your home directory: `git clone https://github.com/carlbuchmann/iac-dev`
  5. Edit `./iac-dev/roles/ansible-engine/main.yml` and enter your active directory domain information (and remove sample data!)
  6. run playbook: `sudo ansible-playbook iac-dev.yml`
  7. launch vscode: `code` and install recommended extensions!

## Future additions

### Things that still need to be done manually

- Install recommended vscode extentions:

  - [YAML Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml_)
  - [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
  - [Jinja](https://marketplace.visualstudio.com/items?itemName=wholroyd.jinja)
  - [PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)
  - [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
  - [Ansible](https://marketplace.visualstudio.com/items?itemName=vscoss.vscode-ansible)
  - [Excel Viewer](https://marketplace.visualstudio.com/items?itemName=GrapeCity.gc-excelviewer)
  - [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
  - [Visual Studio Team Services](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team)

## PRs welcome

Please submit a PR to help enhance this playbook!