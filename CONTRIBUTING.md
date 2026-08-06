# Contributing

Refer to the [Ansible community guide](https://docs.ansible.com/ansible/devel/community/index.html).

## Development environment

The development and test tooling is managed with [uv](https://docs.astral.sh/uv/):

```console
uv sync
uv run pre-commit install
```

## Molecule tests

Each role has a molecule scenario in `extensions/molecule/`. The scenarios run
in rootless podman containers and use the molecule `default` driver, so no
driver plugin is required:

```bash

# e.g.
uv run molecule test -s icinga2_agent
uv run molecule test -s icinga2_client

# list all scenarios
uv run molecule list
```

The scenarios use Debian 13 by default ; set `MOLECULE_DISTRO=debian12` to run
them against Debian 12.

## Opening a pull request

After all tests are green, it's time to open a pull request! Please try to keep the scope of a pull request as
small as possible, to keep review efforts to a minimum.

For the title, make sure to follow conventional commits. A triage bot will automatically assign a labal to the PR.
The label as well as the title of the pull request will then be used to generate the antsibull changelog.

## Create a new release

To create a new release, follow these steps:

1. Manually trigger the [draft-release](https://github.com/adfinis/ansible-collection-icinga2/actions/workflows/draft-release.yml) workflow.
2. Wait for this workflow to open a "Changelog updated" PR.
3. Review and merge this PR.
4. Head over to the [release section](https://github.com/adfinis/ansible-collection-icinga2/releases) and promote the new "draft" release, to an actual release.
