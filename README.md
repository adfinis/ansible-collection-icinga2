# Adfinis Icinga2 Collection

This repository contains the `adfinis.icinga2` Ansible Collection. It
consolidates the former standalone roles `adfinis.icinga2_agent`,
`adfinis.icinga2_client`, `adfinis.icinga2_master` and `adfinis.icinga2_web`
into a single collection.

<!--start requires_ansible-->
<!--end requires_ansible-->

## External requirements

Some modules and plugins require external libraries. Please check the
requirements for each plugin or module you use in the documentation to find out
which requirements are needed.

## Included content

<!--start collection content-->
<!--end collection content-->

### Roles

| Role | Description |
| ---- | ----------- |
| [`adfinis.icinga2.icinga2_agent`](roles/icinga2_agent/README.md) | Install the Icinga 2 package and repositories |
| [`adfinis.icinga2.icinga2_client`](roles/icinga2_client/README.md) | Configure an Icinga 2 satellite/client (zones, certificates, API) |
| [`adfinis.icinga2.icinga2_master`](roles/icinga2_master/README.md) | Configure an Icinga 2 master (zones, IcingaDB, notifications) |
| [`adfinis.icinga2.icinga2_web`](roles/icinga2_web/README.md) | Install and configure Icinga Web 2 (modules, LDAP, Grafana) |

The `icinga2_client`, `icinga2_master` and `icinga2_web` roles automatically
pull in `icinga2_agent` through their role dependencies. Variables keep their
role-name prefix (`icinga2_agent_*`, `icinga2_client_*`, `icinga2_master_*`,
`icinga2_web_*`); see each role's README for details.

Example playbook:

```yaml
- hosts: monitoring_masters
  roles:
    - adfinis.icinga2.icinga2_master
    - adfinis.icinga2.icinga2_web

- hosts: monitored_servers
  roles:
    - adfinis.icinga2.icinga2_client
```

## Using this collection

```bash
    ansible-galaxy collection install adfinis.icinga2
```

You can also include it in a `requirements.yml` file and install it via
`ansible-galaxy collection install -r requirements.yml` using the format:

```yaml
collections:
  - name: adfinis.icinga2
```

To upgrade the collection to the latest available version, run the following
command:

```bash
ansible-galaxy collection install adfinis.icinga2 --upgrade
```

You can also install a specific version of the collection, for example, if you
need to downgrade when something is broken in the latest version (please report
an issue in this repository). Use the following syntax where `X.Y.Z` can be any
[available version](https://galaxy.ansible.com/adfinis/icinga2):

```bash
ansible-galaxy collection install adfinis.icinga2:==X.Y.Z
```

See
[Ansible Using Collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html)
for more details.

## Release notes

See the
[changelog](https://github.com/adfinis/ansible-collection-icinga2/blob/main/CHANGELOG.rst).

## Roadmap

<!-- Optional. Include the roadmap for this collection, and the proposed release/versioning strategy so users can anticipate the upgrade/update cycle. -->

## More information

<!-- List out where the user can find additional information, such as working group meeting times, slack/matrix channels, or documentation for the product this collection automates. At a minimum, link to: -->

- [Ansible collection development forum](https://forum.ansible.com/c/project/collection-development/27)
- [Ansible User guide](https://docs.ansible.com/ansible/devel/user_guide/index.html)
- [Ansible Developer guide](https://docs.ansible.com/ansible/devel/dev_guide/index.html)
- [Ansible Collections Checklist](https://docs.ansible.com/ansible/devel/community/collection_contributors/collection_requirements.html)
- [Ansible Community code of conduct](https://docs.ansible.com/ansible/devel/community/code_of_conduct.html)
- [The Bullhorn (the Ansible Contributor newsletter)](https://docs.ansible.com/ansible/devel/community/communication.html#the-bullhorn)
- [News for Maintainers](https://forum.ansible.com/tag/news-for-maintainers)

## Licensing

GNU General Public License v3.0 or later.

See [LICENSE](https://www.gnu.org/licenses/gpl-3.0.txt) to see the full text.
