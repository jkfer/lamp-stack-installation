# Basic LAMP Installation

#### Prerequisite
 - This playbook was written and tested on CentOS 7
 - Ansible module `expect` is required. Will be installed with yum module


#### Installation:
 - HTTPD
 - MariaDB
 - PHP


#### Configuration:
1. Mariadb configuration options:

  | Configuration  | Setting |
  | -------------- | ------- |
  | Root password | '' |
  | Set root password | 'y' |
  | New password | '{{ mysql_password }}' |
  | Re-enter new password | '{{ mysql_password }}' |
  | Remove anonymous users | 'y' |
  | Disallow root login remotely  | 'n' |
  | Remove test database and access to it | 'n' |
  | Reload privilege tables now | 'y' |

2. Creating a PHP file to have the collection tested
`/var/www/html/info.php`

3. Adding `httpd, https, mysql` to firewall exception



### Other Notes
- Vault and mysql password (mysql_password) both set to *123456* for testing
- For Mariadb, vault encrypted password included inside the playbook for use 
*Reference:
https://docs.ansible.com/ansible/latest/user_guide/vault.html*


### Running
`ansible-playbook lampstack.yml --ask-vault-pass`

