Ansible Role: Tools
=========

This role allows you to initialize a server with the various prerequisites
required:

- installation of additional packages
- SSH configuration change
- changing the MOTD template
- hostname change
- change the prompt for the root user depending on the environment (dev,
  staging, production)

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

You can give a name to your server using the `remote_hostname` variable.
By default, it is set to "HOST000".

    remote_hostname: "WEBSERVER001"

The timezone of your server can also be set with the `timezone` variable.
By default, it is set to Paris time.

    timezone: "Europe/Paris"

A personalized ascii art can be filled in with `motd_ascii_art` variable.
This will be displayed in the MOTD when connecting to the server.
Be careful to respect the line breaks.

A contact email address can be filled in to be also displayed in the MOTD.

By default, the MOTD template will be set to display several useful information
such as:

- FQDN
- distribution version and name
- kernel
- whether the server is virtual or not
- the private and public IPs
- CPUs
- RAM
- swap
- python interpreter version

Additional information can be added using the variable `motd_info`.

Changing the color of the hostname in the prompt depending on the server
environment may be possible. By default, in production, it will be displayed in
red. If the server is flagged as staging, it will be displayed in yellow and
green for development instances. The color of each server can be changed using
the `default_prompt_color` variable where a foreground color code can be
indicated. [See more.](https://www.tecmint.com/customize-bash-colors-terminal-prompt-linux/)

    default_prompt_color: 34
    # Foreground color will be set to blue.

Note: In its current state, this only works for the root user.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: julien_langlois.tools, remote_hostname: "WEBSERVER001", default_prompt_color: 34 }

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2020 by [Julien Langlois](https://github.com/julien-langlois).