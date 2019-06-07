Role Name
=========

Configures the base settings for an ArchLinux-based server. This includes sorting mirrors, updating packages to latest, and creating users.

Requirements
------------

Requires python to already be installed on the host.

Role Variables
--------------

| Variable | Default | Description |
|----------|---------|-------------|
| `packages_require_reboot` | `['linux']` | A list of packages that, if updated, require a system reboot |
| `machine_users` | `[]` | A list of user objects to ensure existence of. Each user has a `name`, `password`, and list of `groups`. If password is empty or undefined, the user's login shell will be set to `/bin/nologin` |
| `machine_groups` | `[]` | A list of group names to ensure existence of. |


Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
- hosts: all
  become: yes
  vars:
    machine_users:
        - name: paul
          password: asdfasdf
          groups: ['wheel', 'users']
    machine_groups:
        - users
        - others
  roles:
    - arch-base
```

License
-------

MIT
