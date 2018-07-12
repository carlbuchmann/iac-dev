# iac-dev - Release 1.1

This playbook configures centos/redhat workstation for `Infrastructure as Code` development with Ansible.

It configures your IaC Development workstation with:

- Remote Desktop (xRDP+TigerVNC) for easy access
- [Microsoft Visual Studio Code](https://code.visualstudio.com/)
- Python
- PowerShell Core for Linux
- Latest Version of Git
- Latest Version of Ansible +
  - WinRM + Kerberos Authentication for windows automation through Ansible
  - Various python libraries for common modules (Azure,AWS,Google Cloud,F5,NAPALM, or add your own!)

## Installation Instructions

  1. Download and install latest version of Centos/RedHat 7 with Gnome Desktop Environment [Centos Download](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Everything-1804.iso).
  2. During installation, create local user and grant administrator privileges
  3. After successful installation, open a terminal window:
  4. [Install Ansible](http://docs.ansible.com/intro_installation.html): `sudo yum install ansible`.
  5. [Install Git](https://git-scm.com/download/linux): `sudo yum install git`
  6. Clone this repository to your home directory: `git clone https://github.com/carlbuchmann/iac-dev`
  7. *Optional* - to enable WinRM: Edit `./iac-dev/roles/ansible-engine/defaults/main.yml` and enter your active directory domain information
  8. run playbook: `sudo ansible-playbook iac-dev.yml`
  9. launch vscode: `code` and install recommended extensions!

## Getting Started with IaC

  1. [Getting Started with VSCode](https://code.visualstudio.com/docs)
  2. [Getting Started with Ansible](https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html)

## Future additions

### Things that still need to be done manually

#### recommended Visual Studio Code extentions

- [YAML Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
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
