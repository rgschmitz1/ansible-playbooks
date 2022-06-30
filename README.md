# ansible-playbooks
These playbooks are for personal educational purposes, these likely do not follow best practices.

## setup
ansible playbooks require an ssh server for connection, this can be installed with the following command.
```
sudo apt update && \
sudo apt install -y ssh-server
```

An ssh key must be created and included under authorized keys to access server via ssh.
```
mkdir ~/.ssh && \
chmod 700 ~/.ssh
ssh-keygen -t rsa -b 4096 -C "<email>"
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys && \
chmod 600 ~/.ssh/authorized_keys
```

## running playbooks
**NOTE:** The `-K` flag is necessary if sudo access requires a password.

```
ansible-playbook -i <inventory>.ini <playbook_name>.yml
```
