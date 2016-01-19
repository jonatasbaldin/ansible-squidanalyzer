squidanalyzer
=============

Ansible role to install and configure SquidAnalyzer in RedHat/CentOS/Debian/Ubuntu.

Requirements
------------

No specific requirements, but running SquidAnalyzer without squid does not make much sense.     
If you want to try it with squid, just `ansible-galaxy install jonatasbaldin.squid3` and add as a role.

Role Variables
--------------

### Gloabals
`squidanalyzer_apache_install`
If true, install a minimal Apache (no vhost) to access SquidAnalyzer. If you want to setup a webserver on your own, see the `templates/squidanalyzer.conf.j2` and use within your module.

`squidanalyzer_web`
Apache root directory, where SquidAnalyzer is installed by default.

`squidanalyzer_package`
Package from SourceForge which will be downloaded.

All the vars in vars/{{ ansible_family_os }} are OS defaults.

Dependencies
------------

None. But, again, to test it nicely, you can use with [jonatabaldin.squid3](https://galaxy.ansible.com/detail#/role/7093).

Example Playbook
----------------

This role comes with a Vagrant file. Just fire a `vagrant up` for testing.     
Once the environemnt is up, just run `vagrant provision` or `ansible-playbook -i tests/inventory tests/test.yml`.     
As the date of this commit, the parameter `host_key_checking=False` it's not working. If some SSH connection error occurs, try to execute `export ANSIBLE_HOST_KEY_CHECKING=False`.

License
-------

MIT

Author Information
------------------

Jonatas Baldin      
<mailto:jonatas.baldin@gmail.com>      
http://deployeveryday.com
