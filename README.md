# Ansible

# Ubuntu

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

Базы команд:
ansible -doc -l - список всех команд

ansible all -m get_url -a "url=https://postimg.cc/mtq7PTH1 dest=/home" -b -K

ansible all -m file -a "path=/home/privet.txt state=absent" -b -K

ansible all -m copy -a "src=privet.txt dest=/home mode=777" -b -K

ansible all -m shell -a "mkdir /home/den/DENIS"

ansible all -m apt -a "name=stress state=absent" -b -K

ansible all -m apt -a "name=stres state=installed" -b -K

ansible -doc -l

### Чтобы запускатьplaybook без пароля на управляемых хостах


Разрешить sudo без пароля
sudo visudo

Добавить в конец файла:

username ALL=(ALL) NOPASSWD: ALL
