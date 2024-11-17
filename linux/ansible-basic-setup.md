---
description: This basic setup is for another linux machine on-premise
icon: book-open
---

# Ansible: Basic Setup

Update and install ansible.

```bash
sudo apt update
sudo apt install ansible -y
```

First, create our inventory.

```bash
mkdir ansible
cd ansible
sudo nano inventory.yml
```

Write this to inventory.yml

```yaml
[vps]
vps_ip_address ansible_user=user ansible_port=port_number
```

Test this inventory config.

```bash
ansible -i inventory.yml vps -m ping
```

The output should be like this:

```bash
IP address VPS | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
```

You are done for inventory. Next, you should create playbook.&#x20;

Playbook have many things to do, for this example this playbook is for update and upgrade apt(s).

```
sudo nano playbook.yml
```

Write this to playbook.yml

```yaml
---
- name: Update and Upgrade APT packages
  hosts: all
  become: true
  tasks:
    - name: Update APT package cache
      apt:
        update_cache: yes

    - name: Upgrade all APT packages
      apt:
        upgrade: dist
        autoremove: yes
        autoclean: yes
```

* `hosts: all` - Specifies that the playbook will be run on all hosts listed in the inventory. You can replace all with a specific group, such as vps.
* `become: true` - Instructs Ansible to use superuser (root) privileges when running the task.
*   `Tasks:`

    `Update APT package cache`: Runs apt-get update to update the package index.&#x20;

    `Upgrade all APT packages`: Runs apt-get dist-upgrade to safely upgrade all packages, remove unnecessary ones, and flush the cache.

***

How to run ansible playbook.

```bash
ansible-playbook -i inventory.yml playbook.yml
```
