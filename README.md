zabbix_add_host
=========

Add hosts to Zabbix server instances with certificate validation enabled.

### When should I consider using this role?
If you have deployed certificates to your Zabbix clients and want to make use of certification validation and don't want to dive too deep into
[certificates and Zabbix](https://www.zabbix.com/documentation/current/en/manual/encryption/using_certificates).

If you only want to add hosts to the Zabbix server, please make use of these excellent modules instead:
- [`community.zabbix.zabbix_host`](https://docs.ansible.com/ansible/latest/collections/community/zabbix/zabbix_host_module.html)
- [`zabbix.zabbix.zabbix_host`](https://catalog.redhat.com/software/collection/zabbix/zabbix)

This role's purpose is to ease the entrance level of certificate validation with Zabbix. Expert Zabbix and Ansible users have surely figured this out already :slightly_smiling_face:

Requirements
------------

This role requires following collections (specified via `collections/requirements.yml`):
- [`zabbix.zabbix`](https://catalog.redhat.com/software/collection/zabbix/zabbix): v1.1.1 or greater
- [`community.crypto`](https://docs.ansible.com/ansible/latest/collections/community/crypto/index.html): v2.3.2 or greater

**Note**: To make use of Red Hat's certified collections, you need to be a Red Hat subscriber. If you don't own any subscriptions, you can make use of 
[Red Hat's Developer Subscription](https://developers.redhat.com/articles/faqs-no-cost-red-hat-enterprise-linux) which is provided at no cost by Red Hat.

Role Variables
--------------

| variable                                     | default                      | required | description                                                                    |
| :---------------------------------           | :--------------------------- | :------- | :----------------------------------------------------------------------------- |
| `zba_api_host`                               | unset                        | true     | host name of the Zabbix server instance serving the API                        |
| `zba_api_user`                               | unset                        | true     | user to authenticate with to the Zabbix API                                    |
| `zba_api_password`                           | unset                        | true     | password of the user connecting to the Zabbix API                              |
| `zba_api_port`                               | `443`                        | false    | port of the Zabbix server API                                                  |
| `zba_api_use_ssl`                            | `true`                       | false    | whether to connect to the Zabbix API via SSL                                   |
| `zba_api_validate_certs`                     | `true`                       | false    | whether to validate certificates when connecting to the API                    |
| `zba_cert_path`                              | unset                        | false    | path to the certificate to extract issuer and subject from                     |
| `zba_api_url`                                | unset                        | false    | use when Zabbix is served via a non-default path, e.g. `/zbx`                  |
| `zba_http_login`                             | unset                        | false    | HTTP basic authentication user name                                            |
| `zba_http_password`                          | unset                        | false    | HTTP basic authentication password                                             |

Additionally, all variables of the module [`zabbix.zabbix.zabbix_host`](https://console.redhat.com/ansible/automation-hub/repo/published/zabbix/zabbix/content/module/zabbix_host/)
can be used (see example below).

This role will pass all variables *currently* (as of 2023-10-18) known for
[`zabbix.zabbix.zabbix_host`](https://console.redhat.com/ansible/automation-hub/repo/published/zabbix/zabbix/content/module/zabbix_host/) to the module.

Dependencies
------------

None

Example Playbook
----------------

```
---
- name: 'Add hosts to a Zabbix instance'
  hosts: 'all'
  become: false
  gather_facts: false
  roles:
    - role: 'zabbix_add_host'
  vars:
    zba_api_host: 'zabbix.example.com'
    zba_api_user: !vault |
          $ANSIBLE_VAULT;1.1;AES256
    zba_api_password: !vault |
          $ANSIBLE_VAULT;1.1;AES256
          [..]
    zba_api_port: 443
    zba_api_use_ssl: true
    zba_api_validate_certs: true
    zba_cert_path: '/etc/zabbix/zabbix_agentd.d/certs/zbx.agent.cert.pem'
    zba_api_url: '/zbx'
    zba_http_login: !vault |
          $ANSIBLE_VAULT;1.1;AES256
    zba_http_password: !vault |
          $ANSIBLE_VAULT;1.1;AES256
    # variables for the module zabbix.zabbix.zabbix_host
    description: '{{ hostvars[inventory_hostname].ansible_fqdn }}'
    host: '{{ hostvars[inventory_hostname].ansible_fqdn }}'
    name: '{{ hostvars[inventory_hostname].ansible_fqdn }}'
    state: 'present'
    status: 'enabled'
    tls_accept: 'cert'
    tls_connect: 'cert'
    hostgroups:
      - 'Linux servers'
    macros:
      - macro: '{$NET.IF.IFNAME.NOT_MATCHES}'
        value: >-
          (^Software Loopback Interface|^NULL[0-9.]*$|^[Ll]o[0-9.]*$|
          ^[Ss]ystem$|^Nu[0-9.]*$|^veth[0-9a-z]+$|docker[0-9]+|
          br-[a-z0-9]{12}|cni-podman[0-9]+)
        description: >-
          Filter out loopbacks, nulls, docker veth links and docker0 bridge
          by default, as well as podman network interfaces
        type: 'text'
    
      - macro: '{$VFS.FS.FSNAME.NOT_MATCHES}'
        value: >-
          ^(/dev|/sys|/run|/proc|.+/shm$|/var/lib/containers/storage/overlay)
        description: >-
          Filter out mount-points that do not need monitoring or are not
          capable of being monitored
        type: 'text'
    templates:
      - 'Template App SSH Service'
      - 'Template Module ICMP Ping'
      - 'Template OS Linux by Zabbix agent active'
    interfaces:
      - type: 'agent'
        useip: true
        dns: '{{ hostvars[inventory_hostname].ansible_fqdn }}'
        ip: '{{ hostvars[inventory_hostname].ansible_default_ipv4.address }}'
    inventory_mode: 'manual
...

```

License
-------

GPL-2.0-or-later
