# Playbooks for Provisioning App Servers

## Install Some Dependencies

```bash
gem i mkpasswd
```

## Make sure you copied your key for root

```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub root@ip-address
```

You can install ssh-copy-id on Mac this way:

```bash
brew install ssh-copy-id
```

## Create a password for your new user

```bash
mkpasswd -m sha-512 -S HashSalt
```

## Copy your ssh key to certificates directory

```bash
cp ~./ssh/id_rsa.pub certificates/id_rsa.pub
```

## Install requirements of the playbooks

```sh
ansible-galaxy install -r requirements.yml
```

## Run this

```sh
ansible-playbook bootstrap.yml --sudo --ask-sudo-pass
```
