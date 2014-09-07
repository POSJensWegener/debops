## debops

[![Travis CI](https://secure.travis-ci.org/debops/ansible-debops.png)](http://travis-ci.org/debops/ansible-debops) [![test-suite](http://img.shields.io/badge/test--suite-ansible--debops-blue.svg)](https://github.com/debops/test-suite/tree/master/ansible-debops/) [![Ansible Galaxy](http://img.shields.io/badge/galaxy-debops.debops-660198.svg)](https://galaxy.ansible.com/list#/roles/1557)[![Platforms](http://img.shields.io/badge/platforms-debian%20|%20ubuntu-lightgrey.svg)](#)

Download [DebOps](http://debops.org/) source code to user home directory,
ready to be used. This role might be useful to setup Ansible Controller
host automatically.


### Installation

This role requires at least Ansible `v1.7.0`. To install it, run:

    ansible-galaxy install debops.debops



### Role dependencies

- `debops.ansible`



### Role variables

List of default variables available in the inventory:

    ---
    
    # User which will be used to clone and manage debops
    # By default, current system user
    debops_user: '{{ ansible_ssh_user | default(lookup("env","USER")) }}'
    
    # Where DebOps will be cloned, relative to user's $HOME
    debops_path: 'src/github.com/debops/debops'
    
    # URI to DebOps repository which will be cloned
    debops_git_repository: 'https://github.com/ginas/ginas.git'
    
    # git branch to clone
    debops_git_branch: 'master'
    
    # URI of optional inventory repository to clone
    debops_inventory_repository: ""
    
    # git branch of inventory repository to clone
    debops_inventory_branch: 'master'
    
    # Where DebOps inventory repository will be cloned, relative to user's $HOME
    debops_inventory_path: 'src/github.com/debops/debops-inventory'
    
    # Name of a directory inside inventory repository which will be linked as
    # 'inventory' directory inside DebOps repository. See 'site.sh' script for more
    # information
    debops_inventory_name: 'inventory'
    
    # An user account which will be checked for when role creates recursive symlinks
    debops_recursive_user: ""
    
    # Name of a Vagrant inventory directory to link automatically as 'inventory' in
    # main DebOps repository. Specify as 'inventory-<name>'
    debops_vagrant_inventory: ""




### Authors and license

`debops` role was written by:

- Maciej Delmanowski | [e-mail](mailto:drybjed@gmail.com) | [Twitter](https://twitter.com/drybjed) | [GitHub](https://github.com/drybjed)

License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-(gpl-3))

***

This role is part of the [DebOps](http://debops.org/) project. README generated by [ansigenome](https://github.com/nickjj/ansigenome/).
