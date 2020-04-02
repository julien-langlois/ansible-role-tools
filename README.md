Ansible Role: Tools
=========

This role allows you to initialize a server with the various prerequisites
required:

- installation of additional packages
- SSH configuration change
- changing the MOTD template
- hostname change
- change the prompt for the root user

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

You can give a name to your server using the "remote_hostname" variable.

    remote_hostname: "SERVER001"

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: julien_langlois.tools, remote_hostname: "SERVER001" }

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2020 by [Julien Langlois](https://github.com/julien-langlois).