# Quadlet Demo

Mimic the Kubernetes [Example: Deploying WordPress and MySQL with Persistent Volumes](https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/) using Podman, Systemd and Quadlet

## Deploy the demo using Ansible
- Start a target machine
    - The demo was tested on a CentOS Stream 9 based EC2 instance
- On your development machine:
    - Install ansible
        ```
        sudo dnf install ansible-core
        ```
    - Clone this repo
        ```
        git clone https://github.com/ygalblum/quadlet-demo.git
        ```
    - Install the required Galaxy collections
        ```
        ansible-galaxy collection install -r requirements.yml
        ```
    - Create the `inventory.yml` file:
        ```yaml
        all:
          hosts:
            < FQDN or IP of the target machine >:
              ansible_connection: ssh
              ansible_user: < Username to connect with >
              ansible_ssh_private_key_file: < Location of the private key >
        ```
    - Run the playbook
        ```
        ansible-playbook playbook.yml
        ```
