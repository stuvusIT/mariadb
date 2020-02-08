# Mariadb Ansible Role

This ansible role configures a mariadb server.


## Requirements

An apt based packagmanager and systemd


## Role Variables

Read the [mariadb doc](https://mariadb.com/kb/en/mariadb/server-system-variables/) to get to know what vars can be set.

Additionally, these variables can be set:

### mariadb_ensure_databases

List of database names

### mariadb_ensure_users

Dict of users. Each key is a username and the value is a dict with up to three
keys:

- `password` - Optional password
- `host` - Optional host which the user can access the DB from
- `privileges` - Ansible-style MariaDB privilege configuration

## Example Playbook


### Playbook

```yml
hosts: wordpress
roles:
    - role: mariadb
      mariadb_port: 3307
      mariadb_socket: /tmp/mariadb.sock
      mariadb_ensure_databases:
        - wordpress
        - example
      mariadb_ensure_users:
        wordpress:
          password: wp
          privileges: "wordpress.*:ALL"
        admin:
          privileges: "*.*:ALL"
        public_account:
          privileges: "public.*:ALL"
          host: "192.168.1.%"
```


### Result

Sets up a running mariadb instance


## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).


## Author Information

 * [Fritz Otlinghaus (Scriptkiddi)](https://github.com/Scriptkiddi) _fritz.otlinghaus@stuvus.uni-stuttgart.de_
