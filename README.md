Role Name
=========

This Ansible role installs Google Stackdriver monitoring agent.

Install this directory in your role path under the name `stackdriver`:

```
git clone https://github.com/apham0001/ansible-role-stackdriver
```

Requirements
------------

The Google Cloud monitoring API must be enabled.

Role Variables
--------------

By default, no plugins are enabled, in which case the agent will only monitor
certain system resources.
Each plugin is enabled with `stackdriver_plugins`
Only supported plugins are availables in directory ```templates```

```
vars:
  stackdriver_plugins:
    - apache
```

### Apache
default host ```local-stackdriver-agent.stackdriver.com```
default port ```80```

To change default values use ```stackdriver_apache_host``` and ```stackdriver_apache_port```

### Memcached
default host ```localhost```
default port ```11211```

To change default values use ```stackdriver_memcached_host``` and ```stackdriver_memcached_port```

### Mysql
default host ```localhost```
default port ```3306```
default user ```stats```

define mysql password with ```stackdriver_mysql_password```
To change others values use ```stackdriver_mysql_host``` and ```stackdriver_mysql_port``` and ```stackdriver_mysql_user```

### Nginx
default host ```local-stackdriver-agent.stackdriver.com```
default port ```80```

To change default values use ```stackdriver_nginx_host``` and ```stackdriver_nginx_port```

### Redis
default host ```localhost```
default port ```6379```

To change default values use ```stackdriver_redis_host``` and ```stackdriver_redis_port```

If you have a password you can define password with ```stackdriver_redis_password```


Example Playbook
----------------
    vars:
      stackdriver_apache_host: "other_host"
      stackdriver_apache_port: "82"

    roles:
      - apham0001.stackdriver

License
-------

BSD
