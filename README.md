[![build-test](https://github.com/darkwizard242/ansible-role-helm/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-helm/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-helm/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-helm/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/57160?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/57160?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/57160?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helm&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-helm) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helm&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helm) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helm&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helm) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helm&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helm) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-helm?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-helm?color=orange&style=flat-square)

# Ansible Role: helm

Role to install (_by default_) [helm](https://helm.sh/) on **Debian/Ubuntu** and **EL** systems. **helm** is a Package Manager for Kubernetes.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
helm_app: helm
helm_version: 3.11.3
helm_os: linux
helm_arch: amd64
helm_dl_url: https://get.{{ helm_app }}.sh/{{ helm_app }}-v{{ helm_version }}-{{ helm_os }}-{{ helm_arch }}.tar.gz
helm_bin_path: /usr/local/bin
helm_file_owner: root
helm_file_group: root
helm_file_mode: '0755'
```

### Variables table:

Variable        | Description
--------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------
helm_app        | Defines the app to install i.e. **helm**
helm_version    | Defined to dynamically fetch the desired version to install. Defaults to: **3.11.3**
helm_os         | Defines os type. Used for obtaining the correct type of binaries based on OS type. Defaults to: **linux**
helm_arch       | Defines os architecture. Used to set the correct type of binaries based on OS System Architecture. Defaults to: **amd64**
helm_dl_url     | Defines URL to download the helm binary from.
helm_bin_path   | Defined to dynamically set the appropriate path to store helm binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
helm_file_owner | Owner for the binary file of helm.
helm_file_group | Group for the binary file of helm.
helm_file_mode  | Mode for the binary file of helm.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **helm**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.helm
```

For customizing behavior of role (i.e. specifying the desired **helm** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.helm
  vars:
    helm_version: 3.7.0
```

For customizing behavior of role (i.e. placing binary of **helm** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.helm
  vars:
    helm_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-helm/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
