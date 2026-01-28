# PostgreSQL Orchestration (Ansible)

![lint](https://github.com/InformaticsMatters/postgresql-ansible/workflows/lint/badge.svg)

![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/informaticsmatters/postgresql-ansible)

[![CodeFactor](https://www.codefactor.io/repository/github/informaticsmatters/postgresql-ansible/badge)](https://www.codefactor.io/repository/github/informaticsmatters/postgresql-ansible)

A playbook and role to deploy PostgreSQL, designed for execution by [AWX].

This project contains one Ansible role:-

*   **postgresql**

>   Note: The Role is designed to be executed from within our AWX server
    where credentials for the cluster (Kubernetes) reside. If you're not
    running from AWX (discouraged) then you will need to provide
    values for the variables that would be injected by AWX.

As with all of our playbooks you can find the common user-defined variables
in the role's `defaults/main.yaml` and less common variables in
`vars/main.yaml`.

>   If you set `pg_enable_affinity` you will need a node in your cluster with the label
    `informaticsmatters.com/purpose-core` as the PostgreSQL Kubernetes Pod
    affinity  will require this label during scheduling.

## Adding an auxiliary user
As well as the 'standard' postgres user you can optionally also create
a second (auxiliary) user with a database and optional super-user privileges
using the `pg_aux` parameters (see `roles/postgresql/defaults/main.yaml`).

## Fine-tuning postgres with configuration
You can configure any additional database [parameters] using the playbook
variable `pg_configuration`.

---

[awx]: https://github.com/ansible/awx
[parameters]: https://www.postgresql.org/docs/12/config-setting.html
