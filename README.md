## Corvo Staging Infrastructure

Creates a staging environment for Corvo Web Application.

The stack includes;
1. HA Nginx
2. HA HAProxy
3. HA RabbitMQ Cluster with 3 instances
4. HA Redis Sentinel with 3 instances
5. NFS Server for sharing resources between services
6. A Spring Boot Ansible Role for deploying Spring Boot applications as Systemd units.

### Running the Playbook
```
$ ansible-playbook corvo-staging-playbook.yml
```

### Running the Playbook for a Specific Layer

Specifici service(s) can be created by using Ansible `tags`.

An example;
```
$ ansible-playbook corvo-staging-playbook.yml --tags=backend
```

Or with multiple tags;
```
$ ansible-playbook corvo-staging-playbook.yml --tags=common,backend
```
