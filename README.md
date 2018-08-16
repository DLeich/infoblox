Role Name
=========

Role to consume the Infoblox Rest API.

Requirements
------------

Access to the Infoblox Rest API

Role Variables
--------------

- Sensible defaut are configured in defaults/main.yml for the following variables
  - infoblox_url (the infoblox appliance url)
  - infoblox_action (the rest api action can be: create, delete, read, update)
  - infoblox_recordtype (the infoblox record type can be: a, ptr, host, cname)
  - infoblox_view (the infoblox view)

- Variables for Infoblox credentials
  - infoblox_username
  - infoblox_password

- Variables for the field in the API request, the field are docummented in      
  https://www.infoblox.com/wp-content/uploads/infoblox-deployment-infoblox-rest-api.pdf
  The name of the field is prefixed by infoblox_
  - infoblox_ipv4addr
  - infoblox_comment
  - infoblox_canonical
  - infoblox_name


Example Playbook
----------------

```
- hosts: localhost
  connection: local
  gather_facts: false
  vars:
    infoblox_username: 'user'
    infoblox_password: 'pass'
    infoblox_hostname: 'infobloxfqdn'
    infoblox_view: 'default'
  tasks:
  - include_role:
       name: infoblox
    vars:
      infoblox_name: 'newhost.dhconsulting.ch'
      infoblox_ipv4addr: '1.1.1.1'
      infoblox_recordtype: 'host'
      infoblox_action: 'create'

  - include_role:
       name: infoblox
    vars:
      infoblox_name: 'newhost.dhconsulting.ch'
      infoblox_recordtype: 'host'
      infoblox_action: 'delete'

License
-------

BSD