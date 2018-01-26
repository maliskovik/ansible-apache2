# Apache 2 ansible role
This ansible role provisions the tartget with an apache2 installation.  
It also configures it with vhost files and opens firewall on ports for
HTTP and HTTPS.

## Supported platforms
* Ubuntu

## Optional configuration variables
All variables under defaults are there to be overriden if needed.
* apache2_config_root - location of config files on the destination
* apache2_main_config - local apache2 config file to send to server.
* apache2_vhosts_dir - sites-enabled directory on target
* apache2_conf_dir - conf-enabled directory on target
* apache2_http_port: http port to use (opens this port on firewall)
* apache2_https_port: https port to use (opens this port on firewall)
