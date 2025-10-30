[![CI](https://github.com/de-it-krachten/ansible-role-virtualbox/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-virtualbox/actions?query=workflow%3ACI)


# ansible-role-virtualbox

Installs VirtualBox 7.0 including extension pack



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- Red Hat Enterprise Linux 10<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- RockyLinux 10
- OracleLinux 8
- OracleLinux 9
- OracleLinux 10
- AlmaLinux 8
- AlmaLinux 9
- AlmaLinux 10
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 41
- Fedora 42

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Uninstall older versions
virtualbox_remove_old_versions: false
</pre></code>

### defaults/family-Debian.yml
<pre><code>
# Current virtualbox versions
virtualbox_packages:
  - virtualbox-7.2

# List of obsolete virtualbox versions
virtualbox_packages_obsolete:
  - virtualbox-5.0
  - virtualbox-5.1
  - virtualbox-6.0
  - virtualbox-6.1
  - virtualbox-7.0
  - virtualbox-7.1
</pre></code>

### defaults/family-RedHat.yml
<pre><code>
# Disable the check for GPG signed packages
virtualbox_disble_gpg_check: false

# Current virtualbox versions
virtualbox_packages:
  - VirtualBox-7.2

# List of obsolete virtualbox versions
virtualbox_packages_obsolete:
  - VirtualBox-5.0
  - VirtualBox-5.1
  - VirtualBox-6.0
  - VirtualBox-6.1
  - VirtualBox-7.0
  - VirtualBox-7.1
</pre></code>

### defaults/family-Suse.yml
<pre><code>
# Current virtualbox versions
virtualbox_packages:
  - VirtualBox-7.2

# List of obsolete virtualbox versions
virtualbox_packages_obsolete:
  - VirtualBox-5.0
  - VirtualBox-5.1
  - VirtualBox-6.0
  - VirtualBox-6.1
  - VirtualBox-7.0
  - VirtualBox-7.1
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'virtualbox'
  hosts: all
  become: 'yes'
  vars:
    molecule_driver: '{{ lookup(''env'', ''MOLECULE_DRIVER_NAME'') }}'
    virtualbox_disble_gpg_check: true
  tasks:
    - name: Include role 'virtualbox'
      ansible.builtin.include_role:
        name: virtualbox
</pre></code>
