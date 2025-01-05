# Hosts

## Hetzner

To connect via SSH to Hetzner use [the following instructions](https://serverfault.com/questions/295768/how-do-i-connect-to-ssh-with-a-different-public-key):

Make sure the ```~/.ssh/config``` file contains a reference to Hetzner:

``` text
Host prompt-management.vanheemstrasystems.com
  Hostname <hostname_or_ip> # here 167.235.17.108 
  User <username> # here root
  Port 22
  IdentityFile ~/.ssh/id_ed25519_hetzner
  CertificateFile ~/.ssh/id_ed25519_hetzner.pub
  # Disable password authentication for better security
  PasswordAuthentication no
  # Prevent TCP forwarding if not needed
  AllowTcpForwarding no
  # Additional security hardening
  KexAlgorithms curve25519-sha256@libssh.org,diffie-hellman-group16-sha512,diffie-hellman-group18-sha512
  MACs hmac-sha2-512-etm@openssh.com,hmac-sha2-256-etm@openssh.com
  Ciphers chacha20-poly1305@openssh.com,aes256-gcm@openssh.com
  HostKeyAlgorithms ssh-ed25519,rsa-sha2-512,rsa-sha2-256
```
~/.ssh/config

Then all you have to do to connect is:

``` bash
$ ssh prompt-management.vanheemstrasystems.com
```
