# `ansible-role-tailscale-proxy`

This role allows you install and configure the [tailscale-proxy](https://github.com/vexxhost/tailscale-proxy)
service using Ansible.

## Role variables

- `tailscale_proxy_version`: Version to install (optional, default: `0.1.0`)
- `tailscale_proxy_config`: Configuration for the service (required)
- `tailscale_proxy_authkey`: Tailscale authentication key (required)
