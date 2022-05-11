# [mssql](#mssql)

Install and configure mssql on your system.

|GitHub|GitLab|Quality|Downloads|Version|Issues|Pull Requests|
|------|------|-------|---------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-mssql/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-mssql/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-mssql/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-mssql)|[![quality](https://img.shields.io/ansible/quality/)](https://galaxy.ansible.com/buluma/mssql)|[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/buluma/mssql)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-mssql.svg)](https://github.com/buluma/ansible-role-mssql/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-mssql.svg)](https://github.com/buluma/ansible-role-mssql/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-mssql.svg)](https://github.com/buluma/ansible-role-mssql/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.mssql
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: buluma.bootstrap
    - role: buluma.core_dependencies
    - role: buluma.ca_certificates
    - role: robertdebock.microsoft_repository_keys
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for mssql

# mssql_add_repositories can be used to select if you want the repositories installed by this role.
# See vars/main.yml for the location of the repositories. Can be: yes, true or 1.
mssql_add_repositories: yes

# What version to use, currently either 2017 or 2019.
# `2017` is the only working version now, `2019` lacks the required
# mssql-server-agent package.
mssql_version: "2017"

# Select the version of server and server_agent to install.
mssql_server_version: "14.0.3294.2-27"
mssql_server_agent_version: "14.0.3015.40-1"

# mssql_sa_password contains the password for a system administrator.
# The password must be at least 8 characters long and contain characters from
# three of the following four sets:
# - uppercase letters
# - lowercase letters
# - numbers
# - and symbols
mssql_sa_password: "StR0nGp4ss."

# mssql_pid refers to the product key to use. Either:
# - Evaluation
# - Developer
# - Express
# - Web
# - Standard
# - Enterprise
# - A product key (Format: #####-#####-#####-#####-#####)
mssql_pid: Evaluation

# To enable full text search, set this value to yes.
mssql_fts: no
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-mssql/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|
|[buluma.ca_certificates](https://galaxy.ansible.com/buluma/ca_certificates)|[![Build Status GitHub](https://github.com/buluma/ansible-role-ca_certificates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-ca_certificates/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-ca_certificates/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-ca_certificates)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Build Status GitHub](https://github.com/buluma/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-core_dependencies/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-core_dependencies)|
|[robertdebock.microsoft_repository_keys](https://galaxy.ansible.com/robertdebock/microsoft_repository_keys)|[![Build Status GitHub](https://github.com/robertdebock/ansible-role-microsoft_repository_keys/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-microsoft_repository_keys/actions)|[![Build Status GitLab ](https://gitlab.com/robertdebock/ansible-role-microsoft_repository_keys/badges/master/pipeline.svg)](https://gitlab.com/buluma/robertdebock.ansible-role-microsoft_repository_keys)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-mssql/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|amazon|Candidate|
|el|7|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.



If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-mssql/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-mssql/blob/master/CHANGELOG.md)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)
