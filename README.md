# LDAP connector

This is a fork of the Spring Security LDAP connector that incorporates the mapping features of version 1.0.6 but is still compatible with grails 1.3.x

## Configuration changes

The main documentation for this plugin can be found [here](http://grails-plugins.github.io/grails-spring-security-ldap/docs/manual.106/guide/single.html#3.%20Configuration)

There is one noteworthy change and that is support for several group prefixes. See below.

| Name | Default | Description |
-------|---------|--------------
|ldap.authorities.clean.prefix |none| A comma-separated list of prefixes. These will be stripped from the ROLE_xyz name. Note that the prefixes need to be uppercase if ldap.mapper.convertToUpperCase is not explicitly set to false! 
Example: A group name Windstream Inc Users will be converted to ROLE_WINDSTREAM INC USERS and then any prefix configured here will be stripped. Prefixes are sorted by length and the longer ones tested first. |
|ldap.authorities.clean.suffix|none|An optional string suffix to strip from the end of LDAP group names. For example, 'Group' will change Faculty Group to ROLE_Faculty|
|ldap.authorities.clean.dashes|false|Set this to true to replace all dashes with underscores in LDAP group names. For example, Staff-All will become ROLE_Staff_All|
|ldap.authorities.clean.uppercase|false|Set this to true to uppercase all LDAP group names. For example, My_Ldap_Group will become ROLE_MY_LDAP_GROUP. This will only work if ldap.mapper.convertToUpperCase is set to false.|

## Build

Using Grails 1.3.5, run `grails package-plugin`.
