# playbooks
Random ansible playbooks

## Remote deployment as root without ssh-key

Install ansible:

```
pkg install py36-ansible
```

Add hosts:

```
edit /usr/local//etc/ansible/hosts
```

Install ssh-pass to prompt for password:

```
pkg install ssh-pass
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
ansible-playbook plasma-workstation.yaml
```

## Local deployment

Install ansible:

```
pkg install py36-ansible
```

Run the playbook:
```
ansible-playbook plasma-workstation.yaml --connection=local
```

