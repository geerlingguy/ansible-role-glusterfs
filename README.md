# Ansible Role: GlusterFS

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-glusterfs.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-glusterfs)

Installs and configures GlusterFS on Linux.

## Requirements

For GlusterFS to connect between servers, TCP ports `24007`, `24008`, and `24009`/`49152`+ (that port, plus an additional incremented port for each additional server in the cluster; the latter if GlusterFS is version 3.4+), and TCP/UDP port `111` must be open. You can open these using whatever firewall you wish (this can easily be configured using the `geerlingguy.firewall` role).

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    TODO

## Dependencies

None.

## Example Playbook

    - hosts: server
      roles:
        - { role: geerlingguy.glusterfs }

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
