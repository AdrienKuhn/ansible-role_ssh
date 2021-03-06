SSH
=========

This role will secure SSH daemon and configure SSH access

Requirements
------------

None

Role Variables
--------------

```yaml
ssh_port: 22
ssh_kexalgorithms: "curve25519-sha256@libssh.org,ecdh-sha2-nistp521,ecdh-sha2-nistp384,ecdh-sha2-nistp256,diffie-hellman-group-exchange-sha256"
ssh_ciphers: "chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com,aes256-ctr,aes192-ctr,aes128-ctr"
ssh_macs: "hmac-sha2-512-etm@openssh.com,hmac-sha2-256-etm@openssh.com,umac-128-etm@openssh.com,hmac-sha2-512,hmac-sha2-256,umac-128@openssh.com"
ssh_permitrootlogin: no
ssh_pubkeyauth: yes
ssh_listenaddress: 0.0.0.0
ssh_protocol: 2
ssh_useprivilegeseparation: yes
ssh_keyregenerationinterval: 3600
ssh_serverkeybits: 1024
ssh_syslogfacility: AUTH
ssh_loglevel: VERBOSE
ssh_strictmodes: yes
ssh_rsaauthentication: yes
ssh_authenticationmethods: publickey
ssh_ignorerhosts: yes
ssh_rhostsrsaauthentication: no
ssh_hostbasedauthentication: no
ssh_permitemptypasswords: no
ssh_challengeresponseauthentication: no
ssh_passwordauthentication: no
ssh_x11forwarding: yes
ssh_x11displayoffset: 10
ssh_printmotd: no
ssh_printlastlog: yes
ssh_tcpkeepalive: yes
ssh_acceptenv: "LANG LC_*"
ssh_subsystem: "sftp /usr/lib/openssh/sftp-server -f AUTHPRIV -l INFO"
ssh_usepam: yes
```

Dependencies
------------

None

Tests
-----

```
$ cd tests
$ vagrant up --provision
```