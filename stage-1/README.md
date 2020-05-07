# Stage-One

The goal is to begin using ansible as a basic introduction.

## Step One: Installation

Ansible seems to be on most repo package managers. It can be installed using this on ubunutu:
```sh
sudo apt install ansible -y
```
General installation can be done using pip to get the latest version:
```sh
pip install ansible
```

## Step Two: Add a machine into the inventory
This will be added into the `machines` file.

To run a command for example you can use:
```sh
ansible -i machines virtual-hosts -m ping
```
This will return:
```sh
10.0.0.10 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

Breaking down the command `-i` provides a direct reference to a seperate inventory file which is different from the default file at `/etc/ansible/hosts` if you put the content in there you will not need the command `-i machines`. 

`virtual-hosts` describes the group of machines to run this command on which has been defined inside the `machines` file.

The last is `-m ping` this specifies a built in ansible module which will send a ping status to the server and expect a pong response.

## Step Three: Create a role which can be executed on the machine to install a basic package.
```sh
ansible-playbook -i machines playbook.yml --ask-become-pass
```
Need explanation