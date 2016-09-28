ansible-nodenv
============

An Ansible role to manage nodenv that was originally forked from https://github.com/nrser/ansible-nrser.nodenv

The role:

* installs nodenv
* adds the shell path addition and nodenv init call
* installs nodenv-build plugin
* installs nodenv-aliases plugins
* installs node versions defined in the role variable
* install node aliases defined in role variable
* sets a global node version define in role variable

Example usage
----------------

An example of using the role and defining all of the variables:

```
roles:
- role: ansible-nodenv
  nodenv_github_base_url: https://github.com/nodenv
  nodenv_shell_config_file: ~/.bashrc
  nodenv_node_versions: [4.0.0, 5.0.0]
  nodenv_version: v1.0.0
  nodenv_node_aliases:
  - { alias: 'v4.0.0', target: '4.0.0' }
  nodenv_global: 4.0.0
```

To run the nodenv tasks under a specific user you can include the role with the become directive:

```
roles:
- role: ansible-nodenv
  become: deploy
```

License
-------

BSD

Author Information
------------------

* Current version: IoraHealth <https://github.com/IoraHealth>
* Original forked role author: <https://github.com/nrser>
