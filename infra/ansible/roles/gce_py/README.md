gce_py
=========

The role to configure the ansible dynamic inventory via  gce.py

Requirements
------------

- There should be a GCE service account credentials file in a json format

- The structure of the directories looks like:

```bash
├── environments
│   ├── prod
│   │   └── group_vars
│   └── stage
│       └── group_vars
├── playbooks
└── roles
└── ansible.cfg
```

- `ansible.cfg` is located in the root of the ansible repository

Role Variables
--------------

- gce_py_ansible_path - the path to the ansible repository where the dynamic inventory should be configured

- gce_py_env - the environment name (the name of the subdirectory in the environments directory). For example, prod

- gce_py_pem_file_path - the path to a google service account credentials file

- gce_py_client_email - the google service account email address

- gce_py_project_id - GCP project name

Dependencies
------------

None

Example Playbook
----------------

```yaml
    - hosts: localhost
      connection: local
      roles:
         - role: gce_py
           gce_py_ansible_path: /home/user/ansible
           gce_py_env: prod
           gce_py_pem_file_path: /secret/place/gce-service-account.json
           gce_py_client_email: google.service.account@gmail.com
           gce_py_project_id: Infra-1234
```

License
-------

BSD

Author Information
------------------
