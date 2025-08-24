# Before run ansible playbook

1) Create credentials.yml ansible vault file

```sh
ansible-vault create credentials.yml
```

2) Set parameters inside the vault

```yaml
ansible_su_pass: <root password>
ansible_su_user: <ssh user>
ansible_password: <ssh user password>
db_url: <database string connection>
device_password_size: <password length>                         
```

3) Create inventory.yml file

```yaml
lyra_hosts:
  hosts:
    lyra:
      ansible_port: <ssh port>
      ansible_host: <dns/ip>
      ansible_user: <user>
```

4) Run playbook

```
ansible-playbook deploy.yml -i inventory.yml --ask-vault-pass
```