# Apache-virtual-hosts
# 📁 Apache Vhost Automation with Ansible (Ubuntu & CentOS)

## 🔧 Description

This project automates the deployment of **Apache virtual hosts** on both **Ubuntu** and **CentOS** servers using Ansible and a **role-based structure**. It is designed to be reusable, scalable, and adaptable across different Linux distributions.

---

## ✅ Key Features

- 🔄 **Role-based architecture**: Modular and maintainable structure following Ansible best practices.
- 🧠 **Default variable fallback**: Uses `test.local` as the default domain if none is provided.
- 💡 **OS detection**: Loads OS-specific settings dynamically (Ubuntu/Debian or CentOS/RedHat).
- 🧰 **Apache package mapping**: Handles `apache2` (Ubuntu) and `httpd` (CentOS) automatically.
- 🌐 **Dynamic vhost templating**: Jinja2 templates configure Apache virtual hosts.
- 🖥️ **Web content provisioning**: Creates an `index.html` with "DevOps Engineer" text.

## 🏗️ Project Structure

```yaml
ansible-vhost-project/
├── inventory
├── playbook.yml
└── roles/
    └── apache_vhost/
        ├── defaults/
        │   └── main.yml
        ├── vars/
        │   ├── Debian.yml
        │   └── RedHat.yml
        ├── tasks/
        │   └── main.yml
        ├── handlers/
        │   └── main.yml
        └── templates/
            ├── index.html.j2
            └── vhost.conf.j2





## 🚀 How to Use

### 1. Add Your Servers to the Inventory
Edit the `inventory` file:

 [web]
 
 ubuntu.hala.com ansible_user=ansible2
 centos.hala.com ansible_user=centos

##  How It Works
Uses ansible_os_family to detect OS (Debian for Ubuntu, RedHat for CentOS)

Loads vars/Debian.yml or vars/RedHat.yml accordingly

Installs the correct Apache package (apache2 or httpd)

Creates the vhost directory and index page

Sets up the virtual host configuration using Jinja2 templates

Enables the vhost and reloads Apache
