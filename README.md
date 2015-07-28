# Ansible Role: GlusterFS

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-glusterfs.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-glusterfs)

Installs and configures GlusterFS on Linux.

## Requirements

For GlusterFS to connect between servers, TCP ports `24007`, `24008`, and `24009`/`49152`+ (that port, plus an additional incremented port for each additional server in the cluster; the latter if GlusterFS is version 3.4+), and TCP/UDP port `111` must be open. You can open these using whatever firewall you wish (this can easily be configured using the `geerlingguy.firewall` role).

This role performs basic installation and setup of Gluster, but it does not configure or mount bricks (volumes), since that step is easier to do in a series of plays in your own playbook. Ansible 1.9+ includes the [`gluster_volume`](https://docs.ansible.com/gluster_volume_module.html) module to ease the management of Gluster volumes.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    glusterfs_default_release: ""

You can specify a `default_release` for apt on Debian/Ubuntu by overriding this variable. This is helpful if you need a different package or version for the main GlusterFS packages (e.g. GlusterFS 3.5.x instead of 3.2.x with the `wheezy-backports` default release on Debian Wheezy).

## Dependencies

None.

## Example Playbook

    - hosts: server
      roles:
        - { role: geerlingguy.glusterfs }

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
