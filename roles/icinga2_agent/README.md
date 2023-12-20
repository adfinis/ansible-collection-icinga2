ROLE ICINGA2\_AGENT
===================

[![image](https://img.shields.io/github/license/adfinis/ansible-role-icinga2_agent.svg?style=flat-square)](https://github.com/adfinis/ansible-role-icinga2_agent/blob/master/LICENSE)

[![image](https://img.shields.io/github/actions/workflow/status/adfinis/ansible-role-icinga2_agent/ansible-ci.yml?style=flat-square)](https://github.com/adfinis/ansible-role-icinga2_agent/actions)

[![image](https://img.shields.io/badge/galaxy-adfinis.icinga2_agent-660198.svg?style=flat-square)](https://galaxy.ansible.com/adfinis/icinga2_agent)

This role is used to install the Icinga2 agent and the nagios plugins.

Requirements
------------

This role requires the EPEL repositories to be configured on the target
system. The following role is suggested:
[adfinis.pkg\_mirror](https://galaxy.ansible.com/adfinis/pkg_mirror)

On RHEL and OracleLinux the optional repo needs to be configured on the target system as well.

Role Variables
--------------

``` {.sourceCode .yaml}
icinga2_agent_yum:
  # The Icinga yum repository
  repo: "http://packages.icinga.com/epel/$releasever/release/"
  # The icinga signing key
  key: "http://packages.icinga.com/icinga.key"

icinga2_agent_apt:
  # The Icinga apt repository
  repo: "deb http://packages.icinga.com/{{ ansible_distribution|lower }} icinga-{{ ansible_distribution_release }} main"
  # The icinga signing key
  key: "http://packages.icinga.com/icinga.key"
```

Dependencies
------------

This role has no direct dependency to other roles.

Example Playbook
----------------

``` {.sourceCode .yaml}
- hosts: servers
  roles:
     - { role: adfinis.icinga2_agent }
```

License
-------

[GPL-3.0](https://github.com/adfinis/ansible-role-icinga2_agent/blob/master/LICENSE)

Author Information
------------------

icinga2\_agent role was written by:

-   Adfinis AG \| [Website](https://www.adfinis.com/) \|
    [Twitter](https://twitter.com/adfinis) \|
    [GitHub](https://github.com/adfinis)
