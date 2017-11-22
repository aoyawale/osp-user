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
username:
user_descript:
user_status:
user_passwd:
user_passwd_create:
```
```

osp_user:
  api:
    auth:
      auth_url: "http://192.168.0.1:35357/v.20"
      username: "admin"
      password: "{{ keystone_admin_password }}"
      project_name: "admin"
    auth_type: "password"
    endpoint_type: "admin"
    region_name: "RegionOne"
    keystone_version: "2"
  users:
    - admin:
        username:
        user_email:
        user_description:
        user_status:
        user_passwd:
        user_passwd_create:
        user_project:
    - user:
        username:
        user_email:
        user_description:
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
