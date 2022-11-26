install_mysql
=========

Role for installing mariadb on CentOS 9.

Requirements
------------

Only available on CentOS 9

Role Variables
--------------

\vars/main.yml\

\mysql_databases:\
  \- name: app\
\mysql_packages:\
  \- mariadb\
  \- mariadb-server\
  \- python3-PyMySQL\
 
defaults/main/main.yml\

mysql_root_user: root\
mysql_root_password: 12345678\
mysql_root_home: /root\
mysql_socket: /var/lib/mysql/mysql.sock\
mysql_users:\
  \- name: app\
    password: "{{ vault_mysql_users_app_password }}"\

\# Encrypted file\
defaults/main/vault.yml\
vault_mysql_users_app_password:\

Dependencies
------------

None

Example Playbook
----------------

\- name: Instalacion de base de datos mysql\
  hosts: all\
  roles:\
    \- install_mysql


License
-------

BSD

Author Information
------------------

Author: Fernando Rios\
Email: fer.rios.costa@gmail.com\
