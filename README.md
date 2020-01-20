# iac-dev - Release 2.4

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

## Installation Instructions Centos 7 - 1908

1. Create VM with minimum 2 vCPUs and 4096 MB RAM
2. Download and install `CentOS-7-x86_64-DVD-1908.iso` [Centos Download](http://centos.mirror.rafal.ca/7.7.1908/isos/x86_64/).
     - Software Selection: Gnome Desktop + Development Tools & System Adminstation Tools
     - Installation Destination: Automatic partition
     - Configure hostname and network
     - During installation, create local user and make this user administrator
3. After successful installation, open a terminal window:
4. Install latest update: `sudo yum update` and reboot system
5. [Install Ansible](http://docs.ansible.com/intro_installation.html) from epel repo:

      ```bash
      sudo yum install epel-release
      sudo yum install python-pip
      sudo pip install --upgrade pip
      sudo pip install ansible==2.9.3
      ```

6. [Install Git](https://git-scm.com/download/linux) and configure Git user:
     - `sudo yum install git`
     - `git config --global user.email "you@example.com"`
     - `git config --global user.name "Your Name"`
7. Clone this repository to your home directory: `git clone https://github.com/carlbuchmann/iac-dev`
8. change directory to iac-dev `cd iac-dev/`
9. *Optional Customization* - Edit `./iac-dev/host_vars/localhost.yml`:
     - Add/remove `vscode_extensions:` ( recommended extensions will be installed by default )
     - add user to `docker_users:`
10. run playbook: `ansible-playbook iac-dev-desktop.yml --ask-become-pass`
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
