# Hosts

## Hetzner

To connect via SSH to Hetzner use [the following instructions](https://serverfault.com/questions/295768/how-do-i-connect-to-ssh-with-a-different-public-key):

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