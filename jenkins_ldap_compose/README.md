# jenkins_ldap_compose
Docker Compose with LDAP + phpLDAPadmin + LDAP Reset Password Tool

Requires Docker-compose 1.4.0+ (for container_name support)

Contains 3 named containers: jenkins_ldap, jenkins_phpldap, and jenkins_ldapresetpass

## Setup

Requires a volume to save the ldap database, config, and reset-password configuration
By default LDAP data will mount to volume /data/ldap/database and /data/ldap/config

A configuration file for the ldap-reset-password has also been included in the ldap-reset-pass-config folder. Docker-compose will mount to /data/ldap-reset-pass-config which should be this folder with the specified config file.

## Container Info

For more info and settings for specific containers used please see:
LDAP - https://github.com/osixia/docker-openldap
phpLDAPadmin - https://github.com/osixia/docker-phpLDAPadmin
reset-password - https://github.com/issc29/ldap-reset-password
