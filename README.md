# RabbitMQ Cluster Setup with Ansible

This project automates the setup of a RabbitMQ cluster using Ansible.

## Setup

1. Install the required Python packages:

pip3 install -r requirements.txt

text

2. Update the inventory file with your RabbitMQ nodes' connection details:

File: `./inventory`

[rabbitmq]
node1 ansible_host=<host> ansible_user=<user> ansible_password=<password> ansible_port=<port> ansible_sudo_pass=<sudo password>
node2 ansible_host=<host> ansible_user=<user> ansible_password=<password> ansible_port=<port> ansible_sudo_pass=<sudo password>
node3 ansible_host=<host> ansible_user=<user> ansible_password=<password> ansible_port=<port> ansible_sudo_pass=<sudo password>

text

Replace `<host>`, `<user>`, `<password>`, `<port>`, and `<sudo password>` with the appropriate values for each RabbitMQ node.

3. Configure the RabbitMQ credentials in the group variables file:

File: `./group_vars/rabbitmq.yaml`

rabbitmq:
username: <rabbit user>
password: <rabbit password>

text

Replace `<rabbit user>` and `<rabbit password>` with the RabbitMQ administrative user credentials.

## Usage

Run the Ansible playbook to set up the RabbitMQ cluster:

ansible-playbook -i inventory rabbitmq_cluster.yml

text

Make sure `rabbitmq_cluster.yml` is your main playbook file for configuring the cluster.

## Notes

- Ensure all RabbitMQ nodes are accessible via SSH using the specified credentials.
- Sudo access is required on the nodes to install and configure RabbitMQ.
- The playbook assumes a 3-node RabbitMQ cluster; adjust inventory as needed for your environment.
Let me know if you want me to help create or improve the playbook file itself or add further details!
