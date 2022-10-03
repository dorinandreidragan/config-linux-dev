# Configure Linux Machine for Dev Workflow

## Overview

This repo contains an ansible playbook that plays the roles needed to configure
my personal dev workflow.

My dev worfklow is mainly made of the following tools:

* [i3][i3]
* [tmux][tmux]
* [neovim][neovim]

I'm also using:

* [Hack Nerd Fonts][hack nerd fonts]
* [xrdp][xrdp] so that I can connect via remote desktop connection to the linux machine
  and still be able to use [i3][i3]

## Prerequisites

* Install Ansible

  > **Note**: For installation steps see: [Installing Ansible][installing ansible]

* Install NodeJS

  > **Note**: You can install `nvm` in order to manage Node versions

  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash 
  ```

* Open port for `xrdp`

  ```bash
  sudo iptables -I INPUT -p tcp --dport {xrdp-port} -j ACCEPT
  ```

## Configure Dev Workflow

* Run the ansible playbook to configure your machine for dev workflow

  ```bash
  export ansible_user={sudo user}
  export ansible_password={sudo pass}

  ansible-playbook config-playbook.yml -e "ansible_sudo_pass=$ansible_password"
  ```

[i3]: https://i3wm.org/
[tmux]: https://github.com/tmux/tmux/wiki
[neovim]: https://neovim.io/
[hack nerd fonts]: https://github.com/ryanoasis/nerd-fonts/releases/download/2.2.0-RC/Hack.zip
[xrdp]: http://xrdp.org/
[installing ansible]: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
