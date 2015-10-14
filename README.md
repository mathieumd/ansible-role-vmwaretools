# Ansible Role: vmwaretools

This role will help you with installing original vmware-tools form Vmware or
fallback to Open VMware Tools (open-vm-tools).

See [VMware documentation](http://packages.vmware.com/tools/docs/manuals/osp-esxi-51-install-guide.pdf).

# Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see
`defaults/main.yml`):

```yaml
# The version of ESXi host. Possible values can be found here:
# http://packages.vmware.com/tools/esx/index.html
vmwaretools_tools_version: 6.0

# Repository package version. See the files into repos/ folder.
# For example: 9.4.10-1 version for
# .../esx/latest/repos/vmware-tools-repo-RHEL6-9.4.10-1.el6.x86_64.rpm
vmwaretools_repo_version: 9.10.0-1

# The server which holds the YUM repository. Customize this if you mirror
# public YUM repos to your internal network.
vmwaretools_yum_server: http://packages.vmware.com

# The path on *yum_server* where the repository can be found. Customize this if
# you mirror public YUM repos to your internal network.
vmwaretools_yum_path: /tools
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: servers
  roles:
  - { role: peru.vmwaretools, when: ansible_virtualization_type == 'VMware' }
```

## License

BSD

## Author Information

This role was initially created in 2014 by <petr.ruzicka@gmail.com>. See
[Ansible Galaxy page](https://galaxy.ansible.com/list#/roles/2509)

