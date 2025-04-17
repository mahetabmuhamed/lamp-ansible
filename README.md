# lamp-ansible

##Setup Instructions

###check that Ansible installed on your local machine

![image](https://github.com/user-attachments/assets/97c3bc05-f05e-465a-bbde-5ee6b982ecd0)


##Inventory Structure Explanation

![image](https://github.com/user-attachments/assets/778a3fe2-93eb-4949-afc2-eb97df96810e)


[webservers]: This is the group name that identifies your web server(s).

192.168.17.137: The IP address of the target server.

ansible_user: The SSH username used to connect to the target server.


##How to Run the Playbook


![image](https://github.com/user-attachments/assets/35db4244-82dc-4add-90fd-b787554a844c)


##Notes on Error Handling and Structure
Error Handling:

Missing sudo Password: If you get an error like "Missing sudo password," it means the playbook is trying to run commands that need elevated privileges, but it doesn’t have the sudo password. You can fix this by adding the --ask-become-pass flag when running the playbook, or you can provide the password directly in the inventory/hosts file.

SSH Connection Issues: If the playbook can't connect to your servers, check that the SSH credentials (like ansible_user and ansible_ssh_pass) are set correctly in the inventory/hosts file. Make sure the target machine is reachable over SSH.

Package Installation Failures: If the playbook fails while installing packages (like Apache or MySQL), double-check that your server has an active internet connection and that the package manager (like apt) is set up properly.

Permission Issues: If tasks fail due to lack of permissions, ensure the user on the target machine has the right privileges. You can also set become: yes in the playbook for tasks that need higher privileges.

Structure of the Project:

The project is organized into a few main components:

playbook.yml: This is the main playbook where all the tasks for setting up the LAMP stack are defined.

roles/: This folder contains different roles, like Apache, MySQL, and PHP. Each role is broken down into smaller parts (tasks, files, handlers, variables), making it easy to manage and extend.

inventory/hosts: This file contains the details of the target servers, such as their IP addresses and user credentials. It tells Ansible where to connect and how to log in.
