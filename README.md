# Configure Linux Machine for Dev Workflow

## Prerequisites

* Install Ansible

  > **Note**: For installation steps see: [Installing Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

* Install NodeJS

  > **Note**: You can install `nvm` in order to manage Node versions

  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash 
  ```

* Open port for `xrdp`

  ```bash
  sudo iptables -I INPUT -p tcp --dport {xrdp-port} -j ACCEPT
  ```

## Configure

* Run the ansible playbook to configure your machine for dev workflow

  ```bash
  export ansible_user={sudo user}
  export ansible_password={sudo pass}

  ansible-playbook config-playbook.yml -e "ansible_sudo_pass=$ansible_password"
  ```
