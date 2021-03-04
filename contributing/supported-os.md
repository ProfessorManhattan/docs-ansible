## Supported Operating Systems

All of our roles should run without error on the following operating systems:

* Archlinux (Latest)
* CentOS 7 and 8
* Debian 9 and 10
* Fedora (Latest)
* Ubuntu (16.04, 18.04, 20.04, and Latest)
* Mac OS X (Latest)
* Windows 10 (Latest)

### Other Operating Systems

Although we do not have a timeline set up, we are considering adding support for the following operating systems:

* **Qubes**
* Elementary OS
* Zorin
* OpenSUSE
* Manjaro
* FreeBSD
* Mint

### Code Style for Platform-Specific Roles

If you have a role that only installs software made for Windows 10 then ensure that the tasks are only run when the system is a Windows system by using `when:` in the `tasks/main.yml` file. Take the following `main.yml` as an example:

```yaml
# tasks/main.yml in the Visual Studio role
---
- name: Include variables based on the operating system
  include_vars: "{{ ansible_os_family }}.yml"
  when: ansible_os_family == 'Windows'

- name: Include tasks based on the operating system
  become: true
  block:
    - include_tasks: "install-{{ ansible_os_family }}.yml"
  when: ansible_os_family == 'Windows'
```
