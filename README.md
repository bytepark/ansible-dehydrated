ansible-dehydrated
=========

Ansible role to install dehydrated (https://github.com/lukas2511/dehydrated) for SSL cert management via Let's encrypt on Ubuntu.
Role supports http-01 challenge type so far.

Assumes you have a webserver configured 
(e.g. NGINX to handle the Let's encrypt ACME requests in the WELLKNOWN dir as defined in the dehydrated config)


Requirements
------------

No further requirements besides Bash and dehydrated requirements.
(openssl,  cURL, sed, grep, awk, mktemp)
Role Variables
--------------

```
dehydrated_domains: []
  # - example.com, www.example.com
  # - example.net, www.example.net
  # - example.org
dehydrated_gitclone: /opt/dehydrated
dehydrated_challenge_type: http-01
dehydrated_basedir: /etc/ssl
dehydrated_contact_email: foo@example.com
```

Dependencies
------------

No dependencies.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: bytepark.dehydrated }

License
-------

MIT

Author Information
------------------

bytepark / 2018.

