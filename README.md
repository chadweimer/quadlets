# quadlets

My personal Podman Quadlets

## Ansible

Ansible Playbooks are provided to easily bring these quadlets up and down in a matter similar to docker compose.

### Inventory

There should be hosts defined for at least the following:

- servers
- workstations

Example:
```yaml
all:
  children:
    servers:
      hosts:
        # ...
    workstations:
      hosts:
        # ...
```

### Bring up all services

```bash
ansible-playbook -K|--ask-become-pass [-C|--check] up.yaml
```

- `-C`, `--check` - If you want to dry-run everything before executing.

### Bring down all services

```bash
ansible-playbook -K|--ask-become-pass [-C|--check] down.yaml
```

- `-C`, `--check` - If you want to dry-run everything before executing.
