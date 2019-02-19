# role-wcl-docker
> an ansible role to install, configure and manage docker 


### Installation
```yaml
# requirements.yml
---
- src: https://github.com/wiredcraft-ops/role-wcl-docker.git
  name: wcl-docker
  version: master
```

```sh
ansible-galaxy install -r requirements.yml -p roles
```

### Role Variables

```yaml
# Enable docker Azure China Mirror
docker_china_mirror: false

# Registry
docker_registry_mirror_url: ""
docker_insecure_registry_url: ""

# Customize docker 0 bridge ip
docker0_ip: ""

# Python packages versions
docker_pip_packages:
  - name: docker-py
    version: "1.9.0"
  - name: PyYAML
    version: "3.12"
  - name: docker-compose
    version: "1.9.0"

# Enable pip mirror (default to China when enabled)
# requires a trusted repo - else need to add "--trusted-host DOMAIN"
# e.g. 
# docker_pip_mirror: "http://pypi.douban.com/simple --trusted-host pypi.douban.com"
docker_pip_mirror_enable: false
docker_pip_mirror: https://mirrors.ustc.edu.cn/pypi/web/simple

# Users belonging to the docker group
docker_users: []
```

### Example Playbook

```yaml
- hosts: server
  roles:
    - role: wcl-docker
```