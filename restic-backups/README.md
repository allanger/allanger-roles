Restic Role
=========

Role Variables
--------------
| Variable                              | Required | Default                                                                                              | Choices         | Comments                                                                             |
| ------------------------------------- | -------- | ---------------------------------------------------------------------------------------------------- | --------------- | ------------------------------------------------------------------------------------ |
| restic_self_update                    | yes      | false                                                                                                | true, false     | If true, restic will do self-update even if it's not being installed in current run  |
| restic_keep_last                      | yes      | 7                                                                                                    | any integer     | Restic will not delete the n last snapshots                                          |
| restic_cron_params                    | yes      | name: restic_backup <br /> weekday: "*" <br /> minute: "0" <br /> hour: "0" <br /> user: root <br /> | valid cron data | Params for restic backup cronjob                                                     |
| restic_password                 | yes      |                                                                                                      | any string      | restic password                                                                      |

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
---
- name: Setup restic backups
  vars:
    restic_keep_last: 7
    restic_backup_dirs:
      - /path/to/dir
      - /another/path/to/dir
    restic_cron_params:
      name: restic_backup
      weekday: "*"
      minute: "30"
      hour: "*"
      user: root

  hosts: all
  roles:
    - role: "."
```