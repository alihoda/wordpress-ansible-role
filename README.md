# wordpress-ansible-role

## Description

This ansbile playbook trying to:

- Secure the the managed host(s) by iptables roles;
- Install and configure docker;
- Configure and use a private docker registry as a docker remote registry;
- Up and running a wordpress container.

This playbook contains four roles:

- common: Install packages and hardening the managed host(s).
- docker: Install and configure docker and private registry.
- nginx: Up and running nginx container.
- wordpress: Up and running wordpress container.

## Supported OS

This playbook uses Hashicorp Vagrant Debian box as its playground but it does not limited to Vagrant.

## Variables

|Variable|Description|Type|Default|
|--- |--- |---|--- |
|`base_dir`|Base directory for projects|string|`/srv`|
|`base_domain`|Base domain for services|string|`test.dev`|
|`registry_domain`|Registry service domain|string|`reg.{{ base_domain }}`|
|`wordpress_domain`|Wordpress service domain|string|`wp.{{ base_domain }}`|
|`self_signed_certificate`|Weather or not using self-signed certificate|bool|`true`|
