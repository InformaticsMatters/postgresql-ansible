# PostgreSQL Orchestration (Ansible)

[![Build Status](https://travis-ci.com/InformaticsMatters/postgresql-ansible.svg?branch=master)](https://travis-ci.com/InformaticsMatters/postgresql-ansible)
![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/informaticsmatters/postgresql-ansible)

[![CodeFactor](https://www.codefactor.io/repository/github/informaticsmatters/postgresql-ansible/badge)](https://www.codefactor.io/repository/github/informaticsmatters/postgresql-ansible)

A playbook and Role to deploy PosgreSQL, suitable for execution by
[AWX].

This project contains one Ansible role:-

*   **postgresql**

>   Note: The Role is designed to be executed from within our AWX server
    where credentials for the cluster (Kubernetes) reside. If you're not
    running from AWX (discouraged) then you will need to provide
    values for the variables that would be injected by AWX.

As with all of our playbooks you can find the common user-defined variables
in the role's `defaults/main.yaml` and less common variables in
`vars/main.yaml`.

>   You will need a node in your cluster with the label
    `informaticsmatters.com/purpose=core` as the Pod will require
    this label during scheduling.

## Adding an auxiliary user
As well as the 'standard' postgres user you can optionally also create
a second (auxiliary) user with a database and optional super-user privileges
using the `pg_aux` parameters (see `roles/postgresql/defaults/main.yaml`).

## Fine-tuning postgres with an extra configuration file
You can configure any additional database [parameters] using a postgres
configuration file. An example is present in the root of this project
(`postgres-extra.conf`).

If you need a file, prepare it and then name it using the playbook's
`pg_extra_configuration_file` parameter, which will be injected into the
postgres **Pod** as a **ConfigMap** and processed by postgres as it starts.

---

[awx]: https://github.com/ansible/awx
[parameters]: https://www.postgresql.org/docs/12/config-setting.html
