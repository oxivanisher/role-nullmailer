nullmailer
==========
[![Ansible Lint](https://github.com/oxivanisher/role-nullmailer/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/oxivanisher/role-nullmailer/actions/workflows/ansible-lint.yml)

This role configures the simple relay-only email transport agent [nullmailer](https://github.com/bruceg/nullmailer) as a system default mail program.

Role Variables
--------------

| Name          | Comment                              | Default value | File to be configured |
|---------------|--------------------------------------|---------------|-----------------------|
| nullmailer_from_domain  | The "from" domain. The mailname will be set to `ansible_hostname`.`nullmailer_from_domain`. |           | `/etc/nullmailer/defaultdomain` and `/etc/mailname` |
| nullmailer_allmail_from  | Send all emails from this address. If set empty, this feature is disabled.   |           | `/etc/nullmailer/allmailfrom` |
| nullmailer_admin_address | The email of the system administrator. |           | `/etc/nullmailer/adminaddr` |
| nullmailer_server_address | The email server to be used to send emails. |           | `/etc/nullmailer/remotes` |
| nullmailer_server_port | The email server port to be used to send emails. | `465`          | `/etc/nullmailer/remotes` |
| nullmailer_server_user | The email user to be used to send emails.  |           | `/etc/nullmailer/remotes` |
| nullmailer_server_password | The email user password to be used to send emails.  |           | `/etc/nullmailer/remotes` |

Example Playbook
----------------

```yaml
- name: System email configuration
  hosts: all,!email_server
  collections:
    - oxivanisher.linux_base
  roles:
    - role: oxivanisher.linux_base.nullmailer
```

License
-------

BSD

Author Information
------------------

This role is part of the [oxivanisher.linux_base](https://galaxy.ansible.com/ui/repo/published/oxivanisher/linux_base/) collection, and the source for that is located on [github](https://github.com/oxivanisher/collection-linux_base).
