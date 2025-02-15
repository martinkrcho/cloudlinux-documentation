# Troubleshooting and Known Issues

## Troubleshooting

To troubleshoot and resolve issues, you can use the following log files:

```
/var/log/ubuntu2cloudlinux.log - conversion log 
/var/log/lve-stats.log - lve-stats 
/var/log/dmesg - kernel module 
```

## Knows Issues

1. Please take into account that if one of the [`alt-python37*` packages](/sub-system-ubuntu/troubleshooting/#list-of-alt-python37-packages) is updated, you should execute the following command to ensure the proper functionality of the LVE-stats daemon:

```
# /sbin/service lvestats try-restart
```

#### List of alt-python37* packages:

* alt-python37
* alt-python37-raven
* alt-python37-simplejson
* alt-python37-sqlalchemy
* alt-python37-alembic
* alt-python37-libs
* alt-python37-markupsafe
* alt-python37-setuptools
* alt-python37-contextlib
* alt-python37-mako
* alt-python27-cllib
* alt-python37-prettytable
* alt-python37-logilab-common
* alt-python37-jinja2
* alt-python37-psycopg2
* alt-sqlite

Behavior like this will be fixed in the upcoming versions.

2. LVE statistics work only with SQLite, other databases (e.g. MySQL, postgreSQL) will be available in the following releases.
3. `alt-php*-zts` packages are not available yet.
4. The `tmpreaper package` is used instead of `tmpwatch`.
5. PNG format for LVE Charts does not work correctly on CloudLinux subsystem on Ubuntu (lvechart utility may produce broken images).
