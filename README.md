SAIO Ansible playbook
=========

An Ansible playbook for provisioning a [Swift](http://docs.openstack.org/developer/swift/development_saio.html) and [Swift-on-File](https://github.com/stackforge/swiftonfile/blob/master/doc/markdown/quick_start_guide.md) all-in-one
development environment on Fedora.

## To run:
To provision the VM, run:
 1. `vagrant up`

To run automated tests:
 1. `vagrant ssh`
 1. `cd swiftonfile`
 1. `tox -e py27`
 1. `tox -e functest`

### Running ansible only:
In case you already have a VM created and just wants to execute the ansible playbook, run the following command:
 1. `ansible-playbook site.yml -i "192.168.56.103," --ask-sudo-pass`

####Notes: 
 * Make sure to update to the correct IP address on the command above (it's important to keep the comma ',' at the end) and the `username` and `group` variables in `site.yml`
 * If testing on RHEL/CentOS, enable EPEL repository first.

## Todo:
* Add ability to provide gerrit ssh keys and setup `git review`

