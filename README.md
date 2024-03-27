kafka
=========

Role for kafka kraft mode installation. Optionally can be installed kafka prometheus exporter and created specific topics. 

Role Variables
--------------

To do

Example Playbook
----------------
```
- hosts: servers
  become: yes
  gather_facts: yes

  vars:
    kafka_version: "3.6.0"
    kafka_heap_size: 1G
    kafka_topics_auto_create: false
    kafka_topics:
      - name: test
        replication_factor: 1
        partitions:  1
        retention_bytes: 5368709120
    kafka_ip: "{{ private_ip }}"
    kafka_node_id: "{{ labels.node_id }}"
    kafka_exporter_install: true
    kafka_exporter_version: "1.7.0"

  roles:
    - kafka
```

