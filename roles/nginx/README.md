Role Name
=========

This role up and running the nginx container with its conf files.

Requirements
------------

if you want to use a self-signed certificate, you should have the `crt` and `key` files and add them in the `roles/nginx/files` directory and encrypt them by `ansible-vault` too. You can use the following command to create a self-signed certificate for all of your sub domains: `openssl req -newkey rsa:4096 -nodes -sha256 -keyout domain.key -addext "subjectAltName = DNS:*.domain.com" -x509 -days 365 -out domain.com.crt -subj "/C=xx/ST=xxx/L=xxx/O=xxx/OU=xxx/CN=*.domain.com"`.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

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
