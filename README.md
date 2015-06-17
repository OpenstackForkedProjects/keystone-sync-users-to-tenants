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
 

## LICENSE

```
# Copyright 2015 Zuercher Hochschule fuer Angewandte Wissenschaften
# All Rights Reserved.
#
#    Licensed under the Apache License, Version 2.0 (the "License"); you may
#    not use this file except in compliance with the License. You may obtain
#    a copy of the License at
#
#         http://www.apache.org/licenses/LICENSE-2.0
#
#    Unless required by applicable law or agreed to in writing, software
#    distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
#    WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
#    License for the specific language governing permissions and limitations
#    under the License.
```
