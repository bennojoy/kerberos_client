kerberos_client
===============

This role will configure the host that it is run against as a Kerberos
client.

Requirements
------------

This role requires that you have a working Kerberos server, you know the
realm name, and the client has access to the Kerberos server port.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

    realm_name: EXAMPLE.COM           # The name of the Kerberos Realm
    kdc_hostname: kerberos            # The hostname of the the server
    admin_hostname: kerberos          # The hostname of the Kerberos
                                      # admin server
    dns_lookup_realm: "false"         # If DNS should be looked up for
                                      # the realm
    dns_lookup_kdc: "false"           # If DNS should be looked up for KDC
    ticket_lifetime: "24h"            # The lifetime for the ticket issued
    renew_lifetime: "7d"              # when to renew the lifetime
    forwardable: "true"                   # Obtain a forwardable ticket.

Example
-------

Here is an example which deploys the Kerberos client with the Realm as BENNO.COM and an admin user "root" and password "foobar":

    - hosts: all
      roles:
      - {role: kerberos_client, realm_name: "BENNO.COM", kadmin_user: "root", kadmin_pass: "foobar", kdc_hostname: "foobar" }

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Benno Joy

