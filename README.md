# Ansible
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible

 ssh-keygen -t rsa -b 4096
sudo ssh-copy-id -i /home/den/den_key.pub den@192.168.29.137 ## ложит в домашнюю директорию /.ssh/authorized_keys
