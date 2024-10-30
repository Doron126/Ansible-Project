# **Ansible-Project**
## **Overview**
This project contains Ansible playbooks to automate the setup and configuration of a web server and a database server.
It’s designed for a test environment and includes roles for installing, configuring, and managing essential services.
It's also include cron jobs to run once a week for ongoing maintance.

## **Thecnologies Used**
* Ansible
* Ansible Galaxy
* YAML

## **Instructions**
1. Set up a debian os machine.
   
2. Set up Ansible and Python (Ansible is a Framework uses python):
     "sudo apt update"
     "sudo apt install python3 -y"
     "sudo apt install ansible -y"

4. Create an inventory file using the hosts file in the repository
   The inventory file path is pointed in etc/ansible/ansible.cfg

5. Create a folder for the playbooks and place the playbooks attached to the repository.

6. Create the machines of the hosts file and configure them:
    * Configure the netplan and use the correct static ip according to the hosts file
    * Install openssh, enable and start the ssh:
      "sudo apt update"
      "sudo apt install openssh-server -y"
      "sudo systemctl enable ssh"
      "sudo systemctl start ssh"
    * On the Ansible machine configure SSH key:
      "ssh-keygen -t rsa -b 4096"
      "ssh-copy-id username@vm-ip-address"
    * Install Python:
      "sudo apt install python3 -y"
     

7. Install the roles from Ansible Galaxy:
    "ansible-galaxy install geerlingguy.ntp"
    "ansible-galaxy install geerlingguy.apache"
    "ansible-galaxy install geerlingguy.mysql"
    "ansible-galaxy install weareinteractive.apt"

9. Create and configure the cron jobs:
    "crontab -e"
    inside it add the jobs:
     "0 0 * * 0 /usr/bin/ansible-playbook -i /path/to/inventory /path/to/web_server.yaml"
     "0 0 * * 0 /usr/bin/ansible-playbook -i /path/to/inventory /path/to/db_server.yaml"

10. Test the playbooks by running them manually, insde the folder where the playbooks at run:
     "/usr/bin/ansible-playbook -i /path/to/inventory /path/to/web_server.yaml"
     "/usr/bin/ansible-playbook -i /path/to/inventory /path/to/db_server.yaml"

