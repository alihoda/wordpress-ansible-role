Docker
=========

This role install docker and configures it by modifing `/etc/docker/daemon.json` file (e.g. change registry mirror, log driver and options, and docker data root directory).
It also add a private docker registry which used as docker mirror registry. If you have a self-signed ssl certificated and a unpulished domain for the registry, the role can handle that too.

Requirements
------------

No requirement is neeeded!

Role Variables
--------------

|Variable|Description|Type|Default|
|--- |--- |---|--- |
|`docker_conflict_packages`|Packages that conflict with the docker installation|[]|`['docker.io','docker-doc','docker-compoes','podman-docker','containerd','runc']`|
|`docker_daemon_log_driver`|Log driver for docker|string|`json-file`|
|`docker_daemon_log_opts`|Log options for docker|object|`{max-size: 10m, max-file: '3'}`|
|`docker_daemon_registry_mirrors`|Remote registry for docker|[]|`['https://{{ registry_domain }}']`|
|`docker_depend_packages`|Packages that should be installed before docker installation|[]|`['gnupg','curl','ca-certificates']`|
|`docker_data_disk`|Disk that used for docker data|string|`/dev/sdb`|
|`docker_packages`|Packages that should be installed for docker installation|[]|`['docker-ce','docker-ce-cli','containerd.io','docker-buildx-plugin','docker-compose-plugin']`|
|`docker_pip_packages`|Requeired pip packages that should be installed|[]|`['docker']|
|`docker_registry_base_dir`|Registry project directory|string|`{{ base_dir }}/registry`|
|`docker_registry_sub_dirs`|Registry project sub directories|[]|`['data']`|
|`docker_registry_config_auth_enabled`|If authentication be enabled for registry|bool|`true`|
|`docker_registry_config_auth_htpasswd_realm`|Registry auth htpasswd realm|string|`registry`|
|`docker_registry_config_http_port`|Registry http port|int|`5000`|
|`docker_registry_config_proxy_remoteurl`|Registry proxy remote url|string|`https://registry-1.docker.io`|
|`docker_registry_config_storage_fs_root_dir`|Registry storage filesystem root directory|string|`/data`|
|`docker_registry_users`|Users for docker registry|[]|`[{ name: 'userone', password: '1234' }]`|
|`docker_users`|Users to add to docker group|[]|`['vagrant']`|

Dependencies
------------

No dependency is required.

License
-------

MIT
