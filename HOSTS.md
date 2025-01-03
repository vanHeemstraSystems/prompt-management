# Hosts

## Hetzner

To connect via SSH to Hetzner use the following instructions:

Make sure the ```~/.ssh/config``` file contains a reference to Hetzner:

```
Host hetzner
  Hostname <hostname_or_ip>
  User <username>
  Port 22
  IdentityFile ~/.ssh/hetzner
  CertificateFile ~/.ssh/hetzner.pub
```
~/.ssh/config

Then all you have to do to connect is:

``` bash
$ ssh hetzner
```
