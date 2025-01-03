# Hosts

## Hetzner

To connect via SSH to Hetzner use [the following instructions](https://serverfault.com/questions/295768/how-do-i-connect-to-ssh-with-a-different-public-key):

Make sure the ```~/.ssh/config``` file contains a reference to Hetzner:

``` text
Host hetzner
  Hostname <hostname_or_ip>
  User <username>
  Port 22
  IdentityFile ~/.ssh/hetzner
  CertificateFile ~/.ssh/hetzner.pub
  # Disable password authentication for better security
  PasswordAuthentication no
  # Prevent TCP forwarding if not needed
  AllowTcpForwarding no
```
~/.ssh/config

Then all you have to do to connect is:

``` bash
$ ssh hetzner
```
