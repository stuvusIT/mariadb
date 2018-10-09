# Mariadb Ansible Role

This ansible role configures a mariadb server.


## Requirements

An apt based packagmanager and systemd


## Role Variables

Read the [mariadb doc](https://mariadb.com/kb/en/mariadb/server-system-variables/) to get to know what vars can be set


## Example Playbook


### Playbook

```yml
hosts: wordpress
roles:
    - role: mariadb
      mariadb_port: 3307
      mariadb_socket: /tmp/mariadb.sock
```


### Result

Sets up a running mariadb instance


## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).


## Author Information

 * [Fritz Otlinghaus (Scriptkiddi)](https://github.com/Scriptkiddi) _fritz.otlinghaus@stuvus.uni-stuttgart.de_
