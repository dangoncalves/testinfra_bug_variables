Bug Report
==========

This role is just an example to illustrate a bug that appears in testinfra with
Ansible as a backend when using in conjonction with molecule.

Bug
---

When setting some variables in default/main.yml or in vars/main.yml, these variables
are accessible during the playbook execution. But we cannot access to them during the
verify sequence with testinfra as a verifier.

This is probably due to the fact that testinfra doesn't run within the playbook (see
https://github.com/philpep/testinfra/issues/266#issuecomment-346470406). It could be
interesting if we had a method that permit to access to the playbook variables during
the tests.

How to reproduce the bug
------------------------

Just run `molecule test`

Versions
--------

Ansible: 2.6.1

Molecule: 2.16.0

Testinfra: 1.14.0
