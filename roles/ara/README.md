ARA Role, derived from Robert de Bock's [ARA role](https://github.com/robertdebock/ansible-role-ara)


Role Variables
--------------

To tell Ansible to use ara, these variables can be modified:
- ara_configuration_file can be set and defaults to /etc/ansible/ansible.cfg.
- ara_callback_plugins should point to where ara is installed.

All other (ara) options can be defined by overwriting ara_configuration:
- ara_configuration:
  - option: port
    value: 9191

You can configure ara using this structure:
```
ara_configuration:
  - option: port
    value: 9191
```

These are the settings you can use.

- dir
- database
- host
- port
- logconfig
- logfile
- loglevel
- logformat
- sqldebug
- ignore_parameters
- ignore_empty_generation
- ignore_mimetype_warnings
- playbook_override
- playbook_per_page
- result_per_page