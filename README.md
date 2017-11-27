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
   # This dictionary should include the names of globally-defined roles.
  # Role definitions are in policy.json/yaml files for each OSP project.
  roles:
    - "admin"
    - "_member_"
  # This dictionary defines domains, projects, and groups (as needed).
  # Keystone v2 only supports projects, so the domains and groups are ignored.
  # Even if you use v2, you must define a single, arbitrarily-named domain.
  # If you use v2, you can forego the "groups" dictionary altogether.
  domains:                                        # Dictionary containing list of domains
  - name: default                                 # Name of one of the domains
    projects:                                     # Dicitionary containing list of domain projects
    - name: test1                                 # Name of one of the projects list's projects
      description: "test1 project"                # Description of the project
      admin:                                      # Dictionary containing admin user details
        name: test1admin                          # Name of the project's admin user
        password: secret                          # Initial password for user (change immediately)
        update_password: on_create                # Password update policy; see module docs
        email: test1admin@domain.net              # Admin user's email address
        description: admin user                   # User description
        enabled: True                             # If the account is active
        State: present                            # If the account is there
        default_project:                          # The project the user belongs too
        domain:                                   # What domain they belong too
    - name: test2                                 # Name of another project, followed by it's details
      description: "test2 project"
      admin:
        name: test2admin
        password: secret
        update_password: on_create
        email: test2admin@domain.net
        description: admin user
        enabled: True
        state: present
        default_project:
        domain:
    groups:                                       # Dictionary containing list of domain groups
    - name: "group1"                              # Name of one of the groups
      description: "group1 group"                 # Description of the group
...
Dependencies
------------


Example Playbook
----------------


License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
