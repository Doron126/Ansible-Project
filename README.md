# **Ansible-Project**
## **Overview**
This project contains Ansible playbooks to automate the setup and configuration of a web server and a database server.
It’s designed for a test environment and includes roles for installing, configuring, and managing essential services.

## **Thecnologies Used**
* Ansible
* Ansible Galaxy
* YAML

## **Instructions**
1. Set up a debian os machine.
   
2. Set up Ansible:
   "sudo apt update"
   "sudo apt install ansible -y"

4. Create an inventory file:
   "sudo nano /etc/ansible/hosts"
   structure

6. Create a directory in the Ubuntu server and create there the files added to the project (app.py, requirements.txt, Dockerfile)

7. Create a GitHub repository and push your code, from the directory you created in Ubuntu. type:
   "git init"
   "git add ."
   git commit -m "Initial commit"
   "git remote add origin 'GitHub_repository_URL'"
   "git push -u origin main"

8. Install the Jenkins plugins and configure the pipeline:
   Connect to Jenkins on port 8080 and go to Manage Jenkins > Plugins.
   Install "Git" and "Docker Pipeline" plugins.
   Click on "+ New Item" and then "Pipeline".
   When configuring the pipeline check "GitHub project" and enter the project URL.
   Choose "Pipeline script from SCM" and then "Git" as the SCM with the repository URL, click Save.

9. Run the job with "Builed Now" and check the results, you should see the app in port 5000.
