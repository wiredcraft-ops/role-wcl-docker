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
# Registry
docker_registry_mirror_url: ""
docker_insecure_registry_url: ""

# Pip versions
pip_docker_py_version: "1.9.0"
pip_pyyaml_version: "3.12"
pip_docker_compose_version: "1.9.0"

# Enable pypi ustc mirror
pip_enable_ustc_mirror: false

# Users belonging to the docker group
docker_users: []
```

### Example Playbook

```yaml
- hosts: server
  roles:
    - role: wcl-docker
```