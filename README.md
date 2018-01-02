```Deploy My own CentOS Workstation```

- yum update
- yum install ansible
- ssh-keygen
- cp ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys
- chmod 600 ~/.ssh/authorized_keys
- visudo: add "rchaplin        ALL=(ALL)       ALL"
