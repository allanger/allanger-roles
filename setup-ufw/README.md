UFW Ansible Role
=========

Install and setup ufw


Role Variables
--------------

The `rules` variable is the main variable in this role. You need to declare all ufw rules inside this var. 

Example:
```
# -- Allow http
rules:
  - rule: allow
    port: "80"
    proto: tcp
```

License
-------

BSD

Author Information
------------------
allanger
