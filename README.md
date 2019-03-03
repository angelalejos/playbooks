# playbooks
Random ansible playbooks

## Remote deployment as root without ssh-key

Install ansible:

```
pkg install py36-ansible
```

Make directory for configuration if it does not exist:

```
mkdir /usr/local/etc/ansible/
```

Add hosts:

```
edit /usr/local/etc/ansible/hosts
```

Install ssh-pass to prompt for password:

```
pkg install sshpass
```

Ensure sshd is enabled, configured the client for PermitRootLogin and restart sshd:

```
sysrc sshd_enable="YES"
```

```
edit /etc/sshd/config
```

```
service sshd restart
```

Run the playbook:
```
ansible-playbook-3.6 01-drivers-intel-gpu.yaml --ask-pass
```

## Local deployment as root without ssh

Install ansible:

```
pkg install py36-ansible
```

Run the playbook:
```
ansible-playbook-3.6 01-drivers-intel-gpu.yaml --connection=local
```

