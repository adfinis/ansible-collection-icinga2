========================================
Adfinis Icinga2 Collection Release Notes
========================================

.. contents:: Topics

v0.1.1
======

v0.1.0
======

Release Summary
---------------

Initial release of the ``adfinis.icinga2`` collection, consolidating the standalone roles ``adfinis.icinga2_agent``, ``adfinis.icinga2_client``, ``adfinis.icinga2_master`` and ``adfinis.icinga2_web`` with their full git histories. Role names and variables are unchanged; role dependencies now use collection FQCNs (e.g. ``adfinis.icinga2.icinga2_agent``).

Minor Changes
-------------

- all roles now use the ansible_facts directory instead of the deprecated, injected variables.

Bugfixes
--------

- icinga2_web - fix the ``when`` condition of "Insert icingaweb2 admin password into database", which errored out on fresh installations because the registered result of the password hash task has no ``skipped`` key when the task actually ran.
