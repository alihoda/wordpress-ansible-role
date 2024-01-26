Common Role
=========

An ansible role that help setup and harding of the target servers.
It configures:

- Flush iptables for given chains
- Allow iptables given ports for the given chains
- Install common pakcages

Requirements
------------

There is no modules required. Just the plays of this roles need the `become: true`.

Role Variables
--------------

|Variable|Description|Type|Default|
|--- |--- |---|--- |
|`common_iptables_allow_ports`|Allow specific ports for the specific protocol in the specific chain|[]|`- { port: 22, protocol: tcp, chain: INPUT, comment: "ssh port"}`|
|`common_iptables_flush_chains`|Flush iptables chains|[]|`[ INPUT, OUTPUT ]`|
|`common_iptables_flushed`|Weather or not flush iptables chains|bool|`false`|
|`common_packages`|Packages that should be installed|[]|`['iptables-persistent','python3-pip','python3-virtualenv','python3-setuptools']`|

Dependencies
------------

There is no dependencies!!

Example Playbook
----------------

    - hosts: servers
      become: true
      roles:
        - common
