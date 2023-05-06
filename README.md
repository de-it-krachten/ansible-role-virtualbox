[![CI](https://github.com/de-it-krachten/ansible-role-virtualbox/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-virtualbox/actions?query=workflow%3ACI)


# ansible-role-virtualbox

Installs VirtualBox 7.0 including extension pack



## Dependencies

#### Roles
None

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 36
- Fedora 37<sup>1</sup>

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Uninstall older versions
virtualbox_remove_old_versions: false

# VirtualBox extension pack url
virtbox_extpack: >-
  http://download.virtualbox.org/virtualbox/{{ virtbox_version_minor }}/Oracle_VM_VirtualBox_Extension_Pack-{{ virtbox_version_minor }}.vbox-extpack
</pre></code>


### vars/family-Debian.yml
<pre><code>
virtualbox_packages_obsolete:
  - virtualbox-5.0
  - virtualbox-5.1
  - virtualbox-6.0
  - virtualbox-6.1

virtualbox_packages:
  - virtualbox-7.0
</pre></code>

### vars/family-RedHat.yml
<pre><code>
virtualbox_packages_obsolete:
  - VirtualBox-5.0
  - VirtualBox-5.1
  - VirtualBox-6.0
  - VirtualBox-6.1

virtualbox_packages:
  - VirtualBox-7.0
</pre></code>

### vars/Fedora.yml
<pre><code>
virtualbox_packages_obsolete:
  - VirtualBox-5.0
  - VirtualBox-5.1
  - VirtualBox-6.0
  - VirtualBox-6.1

virtualbox_packages:
  - VirtualBox-7.0
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'virtualbox'
  hosts: all
  become: "yes"
  tasks:
    - name: Include role 'virtualbox'
      ansible.builtin.include_role:
        name: virtualbox
</pre></code>
