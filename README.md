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


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
