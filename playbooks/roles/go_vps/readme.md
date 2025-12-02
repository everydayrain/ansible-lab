# Go Tools Role

This role installs Go and specified Go binaries on target systems.

## Requirements

- Target system must be Debian/Ubuntu or RedHat/CentOS based
- Sudo/root access required

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
go_version: "1.21.5"
go_install_dir: /usr/local/go
gopath: /opt/go
go_binaries: []
```

### Variable Descriptions

- `go_version`: Version of Go to install
- `go_install_dir`: Directory where Go will be installed
- `gopath`: GOPATH directory for Go workspace
- `go_binaries`: List of Go binaries to install

## Example Playbook

```yaml
- hosts: servers
  become: yes
  roles:
    - role: go_tools
      vars:
        go_version: "1.21.5"
        go_binaries:
          - name: httpx
            package: github.com/projectdiscovery/httpx/cmd/httpx@latest
          - name: gobuster
            package: github.com/OJ/gobuster/v3@latest
```

## License

MIT

## Author Information

Created for security tool automation.
