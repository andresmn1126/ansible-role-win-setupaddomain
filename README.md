# Ansible Role for creating an Active Directory Domain on target server
Roles defaults to install DHCP and Print services as well, can be overriden by setting `install_additional_features` to false.

## Usage:
Create vars file and specify required variables

`ad.yml`
```
ad_domain:
  name: DOMAINNAME
  dsrm_pass: SECRET_DSRM_PASSWWORD
```
`playbook.yml`
```
- hosts: windows
  become: true
  vars_file:
    - ad.yml
  roles:
    - ansible-role-win-setupaddomain

