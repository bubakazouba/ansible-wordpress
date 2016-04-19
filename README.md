#RUN
`ansible-playbook playbook.yml -i hosts -u root`


#Configuration
To disable host key checking add the following to etc/ansible/ansible.cfg or ~/.ansible.cfg.

```
[wordpress]
host_key_checking = False
```


To change hosts in `[wordpress]` group modify the `hosts` file.

To modify database credentials and username: `roles/mysql/defaults/main.yml`

To modify nginx website: `roles/nginx/defaults/main.yml`

#Documentation

##Roles

###Wordpress
* Downloads wordpress and unarchive it in /var/www/wordpress directory with configured ownership.

* Creates user `wordpress` in `www-data`.

* Configures `wp-config.php` and fetches random salts for Wordpress.


###PHP
* Installs PHP

###NGINX
* Installs NGINX

* Disables default site

* adds wordpress configuration and enables site.


###MySQL
* Installs MySQL
* Creates wordpress database and user.
* Starts MySQL service.