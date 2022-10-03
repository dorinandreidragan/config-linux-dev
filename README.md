# Configure Linux Machine for Dev Workflow

## Prerequisites

* Make sure you open the port for xrdp

```bash
sudo iptables -I INPUT -p tcp --dport {xrdp-port} -j ACCEPT
```
