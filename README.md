# [Catena](https://github.com/alysoid/catena) Ansible Role: ssh

Secured and hardened [OpenSSH](https://wiki.archlinux.org/title/OpenSSH) (OpenBSD Secure Shell) client - configured with `/etc/ssh/ssh_config` and snippets in `/etc/ssh/ssh_config.d/*.conf` - and [sshd](https://wiki.archlinux.org/title/OpenSSH#Server_usage) (OpenSSH server daemon) - configured with `/etc/ssh/sshd_config`, snippets in `/etc/ssh/sshd_config.d/*.conf` and managed by `sshd.service`.

Default configuration tested with [ssh-audit](https://github.com/jtesta/ssh-audit) v2.5.0 for `OpenSSH 9.0`, compatible with `OpenSSH 7.4+`.

## Role variables

### Basic configuration

```yaml
# Remove all ssh client configuration files
# from `/etc/ssh/ssh_config.d/*.conf`
ssh_client_cleanup: false

# Remove all ssh server configuration files
# from `/etc/ssh/sshd_config.d/*.conf`
ssh_server_cleanup: false

# `inet` for IPv4 Only
# `inet6` for IPv6 Only
# `any` for both IPv4 and IPv6
ssh_address_family: any

# Default TCP port for connections
ssh_client_port: "22"

# TCP port sshd should listen on
ssh_server_ports: ["22"]

# Public keys never accepted by the server
ssh_server_revoked_keys: []

# Host RSA key size in bits
ssh_host_rsa_key_size: 4096
```

### Client Configuration

Please check `defaults/main/client.yml` file.

### Server Configuration

Please check `defaults/main/server.yml` file.
