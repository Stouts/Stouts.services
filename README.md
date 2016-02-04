Stouts.services
===============

Ansible role to setup services.

#### Variables

```yaml
services_enabled: yes                       # Enable the role
services_init: systemd                      # Init system
services_user: root                         # Default user
services_reload: yes                        # Reload when configuration changed
services_systemd_path: /etc/systemd/system  # Where configurations will be placed
services_upstart_path: /etc/init            # Where configurations will be placed
services_chdir: /                           # Default working directory

# Define your services here
# Example:
# services_services:
#   first:
#     exec: echo 1
#   another:
#     exec: uwsgi myapp
#     chdir: /myapp
services_services: {}                       
```


#### Usage

Add `Stouts.services` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
  - Stouts.services

  vars:
    services_services:
    first:
        exec: echo 1
    another:
        exec: uwsgi myapp
        chdir: /myapp
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.services/issues)!
