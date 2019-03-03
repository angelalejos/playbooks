# playbooks
Random ansible playbooks

## Ansible host configuration

Install ansible on the host:

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

## Client configuration

Install ansible on the client:

```
pkg install py36-ansible
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

Clone this repo on server:

```
git clone https://github.com/iXsystems/playbooks/
```

Run the playbook using remote deployment as root without ssh-key:
```
ansible-playbook-3.6 playbooks/01-drivers-intel-gpu.yaml --ask-pass
```

## Local deployment without ansible host

Install ansible:

```
pkg install py36-ansible
```

Clone this repo on client:

```
git clone https://github.com/iXsystems/playbooks/
```

Run the playbook:
```
ansible-playbook-3.6 playbooks/01-drivers-intel-gpu.yaml --connection=local
```

