# postgresql

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/postgresql/status.svg)](https://drone.osshelp.ru/ansible/postgresql)

The role for PostgreSQL installation

## Usage (example)

```yaml
    - role: postgresql
      postgresql_initial_setup: true
      postgresql_global_config_options:
        - {option: unix_socket_directories, value: '/var/run/postgresql'}
        - {option: listen_addresses, value: '*'}
      postgresql_databases:
        - name: test_db1
          lc_collate: 'en_US.UTF-8'
          lc_ctype: 'en_US.UTF-8'
          encoding: 'UTF-8'
          template: 'template0'
          login_host: 'localhost'
          login_password: ''
          login_user: postgres
        - name: test_db2
      postgresql_users:
        - name: test_user
          password: ''
          db: 'test_db1'
          login_host: 'localhost'
          login_password: ''
          login_user: postgres
```

## Available parameters

### Main

Short description here.

| Param | Default | Description |
| -------- | -------- | -------- |
| `postgresql_initial_setup` | `false` | Whether to place initial-setup script (creates datadir if needed) |
| `postgresql_databases` | `[]` | PostgreSQL databases which will create |
| `postgresql_users` | `[]` | PostgreSQL users which will create |
| `postgresql_global_config_options` | See [default vars](https://gitea.osshelp.ru/dtoxin/postgresql/src/branch/bugfix/initial-setup/defaults/main.yml#L10-L12) | Config options for PostgreSQL

## FAQ

...

## Useful links

- [Official documentation](https://www.postgresql.org/docs/)
- [Our article](https://oss.help/kb884)

## TODO

- ...

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
