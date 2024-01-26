Wordpress Role
=========

This role trying to up and running a wordpress container.

Requirements
------------

No requirements!

Role Variables
--------------

|Variable|Description|Type|Default|
|--- |--- |---|--- |
|`wordpress_base_dir`|Wordpress project directory|string|`{{ base_dir }}/wordpress`|
|`wordpress_sub_dirs`|Wordpress sub directories|[]|`['html']`|
|`wordpress_db_root_password`|Database root password|string|-|
|`wordpress_db_password`|Database password|string|-|
|`wordpress_db_user`|Database user|string|`wordpress`|
|`wordpress_db_name`|Database name|string|`wordpress`|

Dependencies
------------

No dependency!
