[![Build Status](https://travis-ci.org/chaosmail/ansible-roles-sublime-text.svg?branch=master)](https://travis-ci.org/chaosmail/ansible-roles-sublime-text)

Sublime Text
============

Ansible role to install sublime-text, package control and sublime-text plugins on CentOS or Ubuntu.

This role is tested via TravisCI on following platforms:
- Ubuntu 18.04 LTS (bionic)
- Ubuntu 16.04 LTS (xenial)
- Ubuntu 14.04 LTS (trusty)
- CentOS 7
- CentOS 6
- Debian 8 (Jessie)
- Debian 9 (Stretch)

Requirements
------------

No requirements.

Role Variables
--------------

##### Set the Sublime-Text version via the `sublime_version` property. Can be one of `"2", "3"`.

    sublime_version: 3

##### Enable package control via the `sublime_package_control` property. This is enabled  by default.

    sublime_package_control: true

Configure sublime plugins that will be installed via `git` using the `sublime_packages` property. Use the format `[plugin1GithubUrl, plugin2GithubUrl, ..]` or `[{name: plugin1GithubUrl, version: plugin1Ref}, ..]`.

    sublime_packages:
      - 'https://github.com/skuroda/Sublime-AdvancedNewFile.git'
      - 'https://github.com/clifford-github/sublime-ansible.git'
      - 'https://github.com/weslly/ColorPicker.git'
      - 'https://github.com/kemayo/sublime-text-git.git'
      - 'https://github.com/jisaacks/GitGutter.git'
      - 'https://github.com/mitsuhiko/jinja2-tmbundle'
      - 'https://github.com/revolunet/sublimetext-markdown-preview'
      - 'https://github.com/SublimeLinter/SublimeLinter3.git'
      - 'https://github.com/Microsoft/TypeScript-Sublime-Plugin.git'

##### Enable licence key via the `sublime_licence` property. This is disabled by default, as `sublime_licence_key` needs to be supplied.

Please use a valid licence key as, while it will import the provided key, sublime will still report as [UNREGISTERED].

    sublime_licence: false
    sublime_license_key: |
                        ----- BEGIN LICENSE -----
                        John Doe
                        Single User License
                        XXXX-XXXXXXX-XXXXXX
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        YYYYYYYY YYYYYYYY YYYYYYYY YYYYYYYY
                        ------ END LICENSE ------


Dependencies
------------

No dependencies.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: chaosmail.sublime-text }

Also see up to date example in repository path: tests/test.yml

License
-------

MIT

Author Information
------------------

Christoph Koerner
