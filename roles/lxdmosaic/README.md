Role Name
=========

Installation of LXD Mosaic

Base on script LXD Mosaic from <https://lxdmosaic.readthedocs.io/en/latest/>

Requirements
------------

A valid installation of LXD with https access.

```
lxc config set core.https_address [::]
lxc config set core.trust_password some-secret-string #remember this you will be asked later
```

And for mariadb external, a valid lxc container with MariaDB

Role Variables
--------------

variable | description
------------ | -------------
app_name | name of app, as you like, but lxdmosaic is fine
role_user | username to create system user
docker_method | To use docker instead of standard `# not available`
docker\_compose\_version | For docker compose version file `# not available`
mysql\_lxdmosaic\_user | user owner of database LXD_Manager
mysql\_lxdmosaic\_user\_passwd | password of owner user
root_user | user with full access to mariadb (default root)
db\_root\_pass | password of root user
mysql_local | set to true if you want to install mariadb on local instance
mariadb_version | version of MariaDB you want to use
mysql\_lxd\_hostname | lxc container with valid install of MariaDB


Dependencies
------------

- LXD =< 4.x
- Ubuntu 20.04

Example Playbook
----------------

```
- name: LXDMosaic | Installation of LxdMosaic
  hosts: hostlxd
  become: yes
  tasks:
    - name: Include Role quanticware.lxdmosaic
      include_role:
        name: quanticware.lxdmosaic
      vars:
        mysql_local: false
        mysql_lxd_hostname: mariadb-master
        mariadb_version: 10.5
```

License
-------

GPL-2.0

Author Information
------------------

QuanticWare

Frédéric GAUTHIER BESNARD

- <https://quanticware.com>
- <https://github.com/QuanticWare>

Thanks to:

- Turtle0x1
  - <https://github.com/turtle0x1/LxdMosaic>
- Mathieu Garcia
  - <https://www.wiseflat.com/>
  - <https://github.com/wiseflat>
- Carmelo Ingrao
  - <https://www.carmelo.fr>
  - <https://github.com/carmelo42>
