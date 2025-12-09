# Ansible

## Ubuntu

$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible

! /etc/ssh/sshd_config убрать пермит логин рут и авторизацию по паролю

ssh-keygen -t rsa -b 4096 - на управляющем сервере

sudo ssh-copy-id -i /home/den/den_key.pub den@192.168.29.137 ## ложит в домашнюю директорию /.ssh/authorized_keys

! sudo apt-get install ssh-askpass

! chmod 600 - ключа приватного
inventory file - hosts
[webservers]
server1 ansible_host=192.168.28.137 ansible_user=den ansible_ssh_private_key_file=/home/den/den_key

создаем anssible.cfg 
host_key_checking = false
inventory = ./hosts


