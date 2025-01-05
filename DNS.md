# DNS

## Versio (Registrar)

| Domain Name | Name Server Group | Name Servers |
| -- | -- | -- |
| vanheemstrasystems.com | 12394-Cloudflare | monroe.ns.cloudflare.com <br/> rick.ns.cloudflare.com |

## Cloudflare (DNS)

| Subdomain | Type | Host | Test DNS Resolution | Test HTTPS Access |
| -- | -- | -- | -- | -- |
| prompt-management | CNAME | your-hetzner-host.com  (Proxied - Orange Cloud) | dig prompt-management.vanheemstrasystems.com | curl -I https://prompt-management.vanheemstrasystems.com |

## Hetzner (Host)

See also [Using a domain to point to a dedicated server](https://www.reddit.com/r/hetzner/comments/1cb1uv5/using_a_domain_to_point_to_a_dedicated_server/)

| IPv6 | Hostname | Server |
| -- | -- | -- |
| 2a01:4f8:1c1e:8c96::1 | .. | prompt-management |

Adding the key in Hetzner's console only applies to NEW servers. For an existing server, we need to add the key directly to the server. Since we can't SSH in yet, we have this option:

Use Hetzner's Console:

- Go to your server in Hetzner Cloud Console
- Click on "Console" or "Emergency Console"
- Log in as root with your password
- Then add your key to the authorized_keys file

Use the Hetzner CLI:

- ssh-keygen -f "/home/user/.ssh/known_hosts" -R "prompt-management.vanheemstrasystems.com"
- ssh-keygen -f "/home/user/.ssh/known_hosts" -R "prompt-management.vanheemstrasystems.com"

In the ~/.ssh/config file add:

```
Host prompt-management.vanheemstrasystems.com
    HostName 167.235.17.108
    User root
    IdentityFile ~/.ssh/id_ed25519_hetzner
    IdentitiesOnly yes
```
