===============
ROLE _TEMPLATE
===============

.. image:: https://img.shields.io/github/license/adfinis-sygroup/ansible-role-icinga2_agent.svg?style=flat-square
  :target: https://github.com/adfinis-sygroup/ansible-role-icinga2_agent/blob/master/LICENSE

.. image:: https://img.shields.io/travis/adfinis-sygroup/ansible-role-icinga2_agent.svg?style=flat-square
  :target: https://travis-ci.org/adfinis-sygroup/ansible-role-icinga2_agent

.. image:: https://img.shields.io/badge/galaxy-adfinis--sygroup.icinga2_agent-660198.svg?style=flat-square
  :target: https://galaxy.ansible.com/adfinis-sygroup/icinga2_agent

This role is used to install the Icinga2 agent.


Requirements
=============

Any pre-requisites that may not be covered by Ansible itself or the role
should be mentioned here. For instance, if the role uses the EC2 module, it
may be a good idea to mention in this section that the boto package is required.


Role Variables
===============

A description of the settable variables for this role should go here, including
any variables that are in defaults/main.yml, vars/main.yml, and any variables
that can/should be set via parameters to the role. Any variables that are read
from other roles and/or the global scope (ie. hostvars, group vars, etc.)
should be mentioned here as well.


Dependencies
=============

This role depends on the EPEL repositories if used on EL based systems.
The following role is suggested: `pkg_mirror <https://galaxy.ansible.com/adfinis-sygroup/pkg_mirror>`_


Example Playbook
=================

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

.. code-block:: yaml

  - hosts: servers
    roles:
       - { role: adfinis-sygroup.icinga2_agent }


License
========

`GPL-3.0 <https://github.com/adfinis-sygroup/ansible-role-icinga2_agent/blob/master/LICENSE>`_


Author Information
===================

icinga2_agent role was written by:

* Adfinis SyGroup AG | `Website <https://www.adfinis-sygroup.ch/>`_ | `Twitter <https://twitter.com/adfinissygroup>`_ | `GitHub <https://github.com/adfinis-sygroup>`_

