# ansible-role-docker-extended

A couple of extra features for [ansible-role-docker](https://github.com/geerlingguy/ansible-role-docker):

- [Docker config](#docker-config)
- [Docker group management](#docker-group-management)

## Status

[![galaxy](https://img.shields.io/ansible/role/24636.svg?style=for-the-badge)](https://galaxy.ansible.com/ricardogama/docker-extended/) [![license](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)](https://raw.githubusercontent.com/ricardogama/ansible-role-docker-extended/master/LICENSE)

## Docker config

This role enables you to create a docker config file, enable it with the `docker_config` variable:

```yaml
docker_config: |-
  {
    "auths": {
      "foo.bar": {
        "auth": "token"
      }
    }
  }
```

A `config.json` file will be created including the content you defined, based on the following defaults:

```yaml
docker_config_dir: /root/.docker
docker_config_owner: root
docker_config_group: root
```

## Docker group management

You can add users to the Docker group by defining the `docker_group_users` variable:

```yaml
docker_group_users:
  - vagrant
  - root
  - foo
```
