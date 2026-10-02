vagrant up

vagrant ssh control

sudo apt update
sudo apt install -y ansible sshpass


ssh-keygen -t rsa -b 4096 -N "" -f ~/.ssh/id_rsa

# copy key target1 and  target2
ssh-copy-id vagrant@192.168.56.11
ssh-copy-id vagrant@192.168.56.12

mkdir ~/ansible-demo && cd ~/ansible-demo
nano inventory.ini

# file inventory.ini
[webservers]
target1 ansible_host=192.168.56.11
target2 ansible_host=192.168.56.12

[all:vars]
ansible_user=vagrant
ansible_ssh_private_key_file=~/.ssh/id_rsa

ansible all -i inventory.ini -m ping


target1 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
target2 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
