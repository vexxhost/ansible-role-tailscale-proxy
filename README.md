# `ansible-role-tailscale-proxy`

This role allows you install and configure the [tailscale-proxy](https://github.com/vexxhost/tailscale-proxy)
service using Ansible.

## Role variables

- `tailscale_proxy_version`: Version to install (optional, default: `0.6.0`)
- `tailscale_proxy_config`: Configuration for the service (required), see the
  [`tailscale-proxy` documentation](https://github.com/vexxhost/tailscale-proxy#configuration)
  for the endpoint options such as `ephemeral`
- `tailscale_proxy_authkey`: Auth key used to register the endpoints (required
  unless `tailscale_proxy_oauth_client_secret` is set)
- `tailscale_proxy_oauth_client_secret`: OAuth client secret with the
  `auth_keys` scope, used instead of `tailscale_proxy_authkey` when set
- `tailscale_proxy_control_url`: Control server to register with, such as a
  Headscale server (optional, default: the Tailscale control server)

The `tailscale_proxy_oauth_client_id` and `tailscale_proxy_tailnet` variables
are only used by versions older than `0.6.0`.

## Headscale

To register the endpoints with Headscale, point the role at the Headscale
server and use an OAuth client secret as Headscale prints it, or a
pre-authentication key in `tailscale_proxy_authkey`:

```yaml
tailscale_proxy_control_url: https://headscale.example.com
tailscale_proxy_oauth_client_secret: hskey-client-...
```
