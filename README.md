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

---

[awx]: https://github.com/ansible/awx
