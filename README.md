Nginx Webserver
=========

This role can be used to setup a Nginx Webserver with cerbot already included.

Requirements
------------

none

Role Variables
--------------
```yaml
---
domain: domain.com      # The domain of your DNS.
subdomain: subdomain    # The subdomain of your DNS A record.
root: /var/www/html     # defines the path to the webserver root dir
proxy_pass_port: "80"   # defines a port for a proxy_pass if needed    
server_aliases:           # if you want to add more A and/or CNAME records as aliases
  - www.subdomain.domain.com
  - subdomain2.domain.com
  - www.subdomain2.domain.com
```
Dependencies
------------

[GeerlingGuy's Cerbot Role](https://github.com/geerlingguy/ansible-role-certbot) -  already included on the nginx webserver role dependencies

Example Playbook
----------------

```yaml
---
- hosts: host

  roles:
    - name: nginx_webserver
      vars:
        domain: domain.com
        subdomain: subdomain
        admin_email: 'mail@domain.com'
        root: /var/www/html
```
License
-------

MIT

Author Information
------------------

[Gabriel Bernardo](https://github.com/gabrielbernardomc)
