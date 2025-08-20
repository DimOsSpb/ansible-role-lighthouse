# Ansible Role: LightHouse


## Description

Deploy LightHouse using ansible.  
[LightHouse is a lightweight GUI interface for ClickHouse](https://github.com/VKCOM/lighthouse) .

> **! Notice**  
This role does not guarantee the correct work. This is the result of the solution of home work at the DevOPS course and an example of using ANSIBLE roles for automatic deployment of services using the example of the LightHouse service installation.

## Requirements

- This version of the role requires debian 12
- Nginx must be preinstalled for the role and configured to provide access to Lighthouse

## Role Variables

| Variables name | Default value      | Description |
|----------------|--------------------|-------------|
| lighthouse_version        | "master"  | "d701335c25cd1bb9b5155711190bad8ab852c2ce" # commit id      |
| lighthouse_rep     | "https://github.com/VKCOM/lighthouse.git"     | Repository   |

## Dependencies

- Git (if not installed, this package will be installed)
- Nginx

## Example Playbook
```yaml
- name: Install lighthouse
  hosts: lighthouse
  tags: 
    - lighthouse  
  become: true
  roles:
    - role: clickhouse
      when: nginx_installed is succeeded
```
## License

MIT

## Author Information

Dmitrii Osipov  
dimosspb@vk.ru
