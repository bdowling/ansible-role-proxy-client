Ansible Role Proxy Client
=========

Configure various proxy related configs, from apt, yum, system wide ...

Requirements
------------

Some proxy server to connect to ... you could use in tandem to [Ansible role squid](https://github.com/shelleg/ansible-role-squid)

Role Variables
--------------

* `proxy_client_system: true`
* `proxy_client_apt: false`
* `proxy_client_yum: false`


Dependencies
------------

A proxy server at some address ... defaults to `http://localhost:8080`

Example Playbook
----------------

Install squid and configure local system wide proxy config on one sigle host

    - hosts: servers
      roles:
         - role: shelleg.squid
         - role: shelleg.proxy-client

Configure client proxy to proxy connections via 17.16.1.99 on port 9090 and only configure proxy for yum ... considering your proxy does that kind of things ;)

    - hosts: servers
      roles:
         - role: shelleg.proxy-client
           proxy_server_host: 172.16.1.99
           proxy_server_port: 9090
           proxy_client_yum: true
           proxy_client_system: false
           

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
