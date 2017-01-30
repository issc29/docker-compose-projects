# jenkins_ldap_compose
Docker Compose with LDAP + phpLDAPadmin

Requires docker-compose 1.4.0+ (for container_name support)

Contains 2 named containers: ldap, phpldapadmin

## Setup

Requires a volume to save the ldap database and config configuration.

By default LDAP data will mount to volume /data/ldap/database and /data/ldap/config

First time use:
* Open a Terminal and run `docker run --volume /data/ldap/database:/var/lib/ldap --volume /data/ldap/config:/etc/ldap/slapd.d  --env LDAP_ORGANISATION="My Company" --env LDAP_ADMIN_PASSWORD="password" --detach osixia/openldap:1.1.7`
* This will initialize the necessary files for first time use of openldap
 * Kill the container that was created. It is only used for first time initialization
* Run `docker-compose up -d` and access phpldapadmin using https://localhost:443
  * Login credentials - user: `cn=admin,dc=example,dc=org` password: `password`

## Container Info

For more info and settings for specific containers used please see:
* LDAP - https://github.com/osixia/docker-openldap
* phpLDAPadmin - https://github.com/osixia/docker-phpLDAPadmin
