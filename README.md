# Ansible Collection - quanticware.lxd


Collection content:
------------

- LXDMosaic (<https://github.com/turtle0x1/LxdMosaic>)


Requirements
------------

A valid installation of LXD with https access.

```
lxc config set core.https_address [::]
lxc config set core.trust_password some-secret-string #remember this you will be asked later
```


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