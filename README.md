# LAMP


![LAMP](https://github.com/user-attachments/assets/ffcfa878-a112-4fc5-882d-13b2216c3042)

# 🚀 LAMP Stack Deployment with Ansible

This Ansible project automates the deployment and configuration of a **LAMP Stack** (Linux, Apache, MySQL, PHP) across multiple servers using best practices such as roles, handlers, blocks, error handling, and environment separation.

---

## 📁 Project Structure

```bash
lamp-ansible/
├── ansible.cfg
├── inventory/
│   ├── dev
├── group_vars/
│   └── all.yml
├── roles/
│   ├── apache/
│   ├── mysql/
│   ├── php/
│   └── firewall/
├── playbook.yml
└── README.md

## Setup Instructions

1.Setup Instructions

![image](https://github.com/user-attachments/assets/e7e0e245-a81d-41c5-90dd-a3e7851db564)

2.Set Up Inventory

![image](https://github.com/user-attachments/assets/4e7d35fd-b275-4397-872b-0c77889b2c3c)


3.Update Group Variables

![image](https://github.com/user-attachments/assets/e4a5b8cb-a2af-42e0-a190-e0bb4e4cff1f)

## How to Run the Playbook

![image](https://github.com/user-attachments/assets/4bd074c5-5598-4353-aa60-8a2d9ebbe9b3)

# What This Playbook Does

Installs Apache and deploys a sample index.php.

Installs and secures MySQL (sets root password, removes test DB, disables remote root login).

Installs PHP and validates Apache can serve PHP pages.

(Bonus) Configures UFW to allow ports 80 and 443.

 ## Error Handling & Structure

Tasks are wrapped in block, rescue, and always blocks for graceful failure.

handlers are notified only when a config change occurs.

Inventory files support environment-based deployment (dev, prod).

Variables are defined cleanly using group_vars.

