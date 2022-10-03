# Configure Linux Machine for Dev Workflow

## Prerequisites

* Install NodeJS

  > **Note** you can install `nvm` in order to manage Node versions

  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash 
  ```

* Open port for `xrdp`

  ```bash
  sudo iptables -I INPUT -p tcp --dport {xrdp-port} -j ACCEPT
  ```
