# Ansible Role: user

An Ansible Role to create/update users and their authorized_keys.

[![Actions Status](https://github.com/tristan-weil/ansible-role-user/workflows/molecule/badge.svg?branch=master)](https://github.com/tristan-weil/ansible-role-user/actions)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| user_list     | []      | a list of <*user entry*> |

### <*user entry*>

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |
| name          | the username |
| authorized_key | an authorized key |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| group         | omit    | the primary group |
| groups        | omit    | the secondary groups |
| append        | True    | *True / False*: to add new groups to the existing list or replace them |
| state         | present | *present / absent*: to add or remove a user |
| shell         | /bin/bash | the shell |
| login_class   | omit    | the login-class (OpenBSD only) |
| system        | False   | *True / False*: to create a system user |
| authorized_key_options | omit | options to add to the authorized key |

## Example Playbook

    - hosts: 'webservers'
      roles:
        - role: 'ansible-role-user'
          user_list:
            - name: 'titou'
              authorized_key: xxxxx

## Todo

None.

## Dependencies

None.

## Supported platforms

See [meta/main.yml](https://github.com/tristan-weil/ansible-role-user/blob/master/meta/main.yml)

## License

See [LICENSE.md](LICENSE.md)
