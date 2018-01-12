# Deploy My own CentOS Workstation

* yum update
* yum install ansible
* ssh-keygen
* cp ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys
* chmod 600 ~/.ssh/authorized_keys
* visudo(uncomment): %wheel  ALL=(ALL)       NOPASSWD: ALL

# How to Run
ansible-playbook deploy-workstation.yml - hosts
