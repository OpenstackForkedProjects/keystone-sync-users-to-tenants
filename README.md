# Keystone Sync Users to Tenants

If you want to have a tenant for each of your users in OpenStack Keystone, look no further. This script does just that. Useful if you have a LDAP backend for your users but you keep the assignments in a different backend.

## Features
* Creates Tenants for users which are enabled
* Disables Tenants for users which are disabled 
* Grants a set of configurable roles to the user in his tenant
* Revokes those roles when the user is disabled
* Blacklisting of users which you don't want to be synced 

## How to run
How you use this script is up to you. Use it manually, via cron or somewhere in your pipeline.

## Configuration
Configuration is currently done in the script itself:

### ROLE_NAMES_TO_GRANT
The names of the roles you want a user to have in his tenant, e.g.:

```
ROLE_NAMES_TO_GRANT = ['_member_', 'heat_stack_owner']
```

### USER_NAMES_TO_IGNORE (Blacklist)
The names of users you want to ignore in the sync process, e.g.:

```
USER_NAMES_TO_IGNORE = ['admin', 'heat', 'keystone']
```

## TODO
* externalise configuration
* allow more flexible blacklist (e.g.: part of the email @companyxyz.com, keystone domain)
* allow a whitelist mode
 
