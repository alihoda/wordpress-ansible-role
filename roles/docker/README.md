Docker
=========

This role install docker and configure a local registry to use as the *mirror-registry*. It also support a self-signed ssl certificate for the registry.

Requirements
------------

This role just needs the self-signed certificate file (if `docker_registry_self_signed` is `true`).

Role Variables
--------------

|Variable|Description|Type|Default|
|--- |--- |---|--- |
|`docker_conflict_packages`|Packages that conflict with the docker installation|[]|`['docker.io','docker-doc','docker-compoes','podman-docker','containerd','runc']`|
|`docker_depend_packages`|Packages that should be installed before docker installation|[]|`['gnupg','curl','ca-certificates']`|
|`docker_packages`|Packages that should be installed for docker installation|[]|`['docker-ce','docker-ce-cli','containerd.io','docker-buildx-plugin','docker-compose-plugin']`|
|`docker_registry_base_dir`|Registry project directory|string|`{{ base_dir }}/registry`|
|`docker_registry_sub_dirs`|Registry project sub directories|[]|`['certs','auth','data']`|
|`docker_registry_config_auth_enabled`|If authentication be enabled for registry|bool|`true`|
|`docker_registry_config_auth_htpasswd_realm`|Registry auth htpasswd realm|string|`registry`|
|`docker_registry_config_http_port`|Registry http port|int|`5000`|
|`docker_registry_config_proxy_remoteurl`|Registry proxy remote url|string|`https://registry-1.docker.io`|
|`docker_registry_config_storage_fs_root_dir`|Registry storage filesystem root directory|string|`/data`|
|`docker_registry_files`|Required files for registry service|[]|`[{ src: 'registry.compose.yml.j2', dest: 'docker-compose.yml' }]`|
|`docker_registry_mirror`|Registry domain|string|`{{ registry_domain }}`|
|`docker_registry_users`|Users for docker registry|[]|`[{ name: userone, password: '1234' }]`|
|`docker_registry_self_signed`|Weather of not use self-signed certificate|bool|`true`|
|`docker_users`|Users to add to docker group|[]|`['vagrant']`|

Dependencies
------------

No dependency is required.

License
-------

MIT
