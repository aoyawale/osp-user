Role Name
=========

This role creates a osp user. This roles vars are similar to other osp roles so they can be used all together.
Requirements
------------


Role Variables
--------------
```
region:
user_cert:
user_key:
user_cacert:
user_endpoint:
zone:
user_project:
user_email:
user_name:
user_descript:
user_status:
user_passwd:
user_passwd_create:
```
```

osp_user:
  api:
  auth:
    auth_url:
    username:
    password:
    project_name:
  auth_type:
  endpoint_type: 
  region_name:
  keystone_version:

  user:
    user_name:
    user_email:
    user_descript:
    user_status:
    user_passwd:
    user_passwd_create:
    user_project:
  
  

Dependencies
------------


Example Playbook
----------------


    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
