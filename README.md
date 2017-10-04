# Ansible Role: os	query

Ansible Role to install and configure osquery for Ubuntu.


## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

Set the osquery deamon name.
    
    osquery_deamon: "osqueryd"

Set the location of the config directory.

    osquery_config_include_dir: "/etc/osquery"

Configure the plugin type. [doc](http://osquery.readthedocs.io/en/latest/development/config-plugins/)

    config_plugin: "filesystem"
    
Configure the logger plugin. [doc](https://osquery.readthedocs.io/en/latest/development/logger-plugins/)

    logger_plugin: "filesystem"

Configure the logger directory.

    logger_path: "/var/log/osquery"

Disable INFO, WARN, and ERROR logs. This will still write results.

    disable_logging: "false"

Splay the scheduled interval for queries.
    
    schedule_splay_percent: 10

Write the pid of the osqueryd process to a pidfile/mutex.

    pidfile: "/var/osquery/osquery.pidfile"

Clear events from the osquery backing store after a number of seconds.

    events_expiry: 3600

A filesystem path for disk-based backing storage used for events and query results.

    database_path: "/var/osquery/osquery.db"

Comma-delimited list of table names to be disabled.

    disable_tables: ""

Enable debug or verbose debug output when logging.

    verbose "true"

Maximum file read size.
    
    read_max: 100000

 Maximum number of events per type to buffer.
 
    events_max: 100000

Enable the schedule monitor.

    enable_monitor: "true"

Host running osquery (hostname, uuid).

    host_identifier: "hostname"

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - apolloclark.osquery

## License

MIT / BSD

## Author Information

This role was created in 2017 by [Apollo Clark](https://www.apolloclark.com/)
