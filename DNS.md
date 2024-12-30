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
