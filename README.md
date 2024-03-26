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
    kafkaVersion: "3.6.0"
    kafkaHeapSize: 1G
    autoCreateTopicsEnable: false
    kafkaTopics:
      - name: test
        replicationFactor: 1
        partitions:  1
        retentionBytes: 5368709120
    exporterInstall: true
    exporterVersion: "1.7.0"

  roles:
    - kafka
```

