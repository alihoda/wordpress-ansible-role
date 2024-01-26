Nginx Role
=========

This role up and running the nginx container with its conf files.

Requirements
------------

if you want to use a self-signed certificate, you should have the `crt` and `key` files and add them in the `roles/nginx/files` directory and encrypt them by `ansible-vault` too. You can use the following command to create a self-signed certificate for all of your sub domains: `openssl req -newkey rsa:4096 -nodes -sha256 -keyout domain.key -addext "subjectAltName = DNS:*.domain.com" -x509 -days 365 -out domain.com.crt -subj "/C=xx/ST=xxx/L=xxx/O=xxx/OU=xxx/CN=*.domain.com"`.

Role Variables
--------------

|Variable|Description|Type|Default|
|--- |--- |---|--- |
|`nginx_base_dir`|Nginx project directory|string|`{{ base_dir }}/nginx`|
|`nginx_sub_dirs`|Nginx sub directories|[]|`['certs','conf','snippets']`|
|`nginx_registry_client_max_body_size`|Max body size for uploading|string|`1024m`|
|`nginx_private_hosts`|Private hosts to added to /etc/hosts|[]|`[{ip:'',domains:''}]`|

Dependencies
------------

Two docker networks should be avaiable: `web` and `reg`.
