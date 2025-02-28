# ansible-wordpress-updates
Ansible playbook to update wordpress (major, themes and plugins).  

## Description
This playbook allows you to update multiple wordpress installations - it automatically scans for all wordpress installations at /var/www.  
Befor the update, it will write a backup of the Database to `/var/www/update-backups`.  
For each step (major, plugin and theme updates) it will print the available updates and ask you, if you really want to run the update.  
WP-CLI is used to run the updates.  

Example:  


Tested with:    
* Debian 12 Server  
* various Wordpress installations

## Getting Started  
### Dependencies  
* Linux server with a wordpress installation
* [Github - WP-CLI](https://github.com/wp-cli/wp-cli) installed on the host ([Installation Guide](https://github.com/wp-cli/wp-cli?tab=readme-ov-file#installing))   
* Ansible

### Installing

#### Wordpress-Hosts:
* Install WP-CLI:
     ([Installation Guide from WP_CLI](https://github.com/wp-cli/wp-cli?tab=readme-ov-file#installing)):
     ```sh
     curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
     php wp-cli.phar --info
     chmod +x wp-cli.phar
     sudo mv wp-cli.phar /usr/local/bin/wp
     ```
     Test, if it was successfull:
     ```sh
     wp --info
     ```

#### Ansible server:

* add the role `wordpress-updates.yml` to your ansible-directory.
* add the server(s) with the wordpress installation(s) in a ansible host-group named [webserver]
* run the playbook

## Version History
* 1.0
    * Initial Release

## Acknowledgments
* [Github - WP-CLI](https://github.com/wp-cli/wp-cli)
