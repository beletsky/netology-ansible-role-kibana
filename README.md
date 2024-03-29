Kibana Role
===========

The role installs Kibana on specified nodes.

Requirements
------------

RHEL- and Debian-like Linux systems are currently supported.

Tested on
---------
- CentOS 7
- Ubuntu
- Debian

Role Variables
--------------

| Variable name      | Default     | Description                                                                   |
|--------------------|-------------|-------------------------------------------------------------------------------|
| kibana_version     | "7.14.0"    | Which version on Kibana should be installed                                   |
| elasticsearch_host | "localhost" | Host or IP address where ElasticSearch is installed and listened on port 9200 |

Example Playbook
----------------

    - hosts: all
      roles:
        - role: kibana
          elasticsearch_host: localhost      

Notes
-----

Kibana is installed using RPM into default directories.

To keep idempotency, the playbook leaves Kibana downloaded binary distribution in the temporary directory `/tmp`. If you don't need it, feel free to remove those files to free some disk space.

License
-------

MIT

Author Information
------------------

Any suggestions for improvements e-mail to [abeletskiy@ppr.ru](mailto:abeletskiy@ppr.ru).
