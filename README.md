

# 🚀 LAMP Stack Cluster with Ansible

Deploy a complete **LAMP (Linux, Apache, MySQL, PHP)** stack using **Ansible** across multiple nodes. This repo includes all necessary roles, configurations, and examples to quickly bootstrap a production-ready or development LAMP cluster.

---

## 📁 Project Structure

lamp-cluster/ ├── inventory.ini # Hosts definition (web, db) ├── playbook.yml # Main deployment playbook ├── group_vars/ │ └── all.yml # Global variables └── roles/ ├── apache/ # Apache installation and vhost ├── php/ # PHP + modules ├── mysql/ # MySQL server ├── mysql_client/ # MySQL client on web nodes └── letsencrypt/ # SSL using Let's Encrypt


---

## ⚙️ Prerequisites

- Ansible 2.10+ installed locally
- RHEL/CentOS 7+ nodes (or compatible)
- SSH access to all nodes
- Internet access for Let's Encrypt SSL

---

## 🚀 Usage

1. Clone the repo

```bash
git clone https://github.com/your-username/lamp-cluster.git
cd lamp-cluster

    Modify inventory.ini and group_vars/all.yml with your node IPs and domain.

    Run the playbook:

ansible-playbook -i inventory.ini playbook.yml

🔐 SSL Support

Uses Certbot to automatically provision Let's Encrypt SSL certificates. Make sure ports 80 and 443 are open and DNS is properly configured.
🔥 Firewall Rules

Firewall ports opened by default:

    80/tcp – HTTP

    443/tcp – HTTPS

    3306/tcp – MySQL (optional, for cross-node access)

✅ Features

    Full LAMP stack installation with one playbook

    Role-based modular structure

    Reusable for dev, staging, and prod

    SSL auto-provisioned using Let's Encrypt

    Apache virtualhost templates with Jinja2
