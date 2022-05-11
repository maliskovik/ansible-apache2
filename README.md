# Apache 2 ansible role
This ansible role provisions the tartget with an apache2 installation.  
It also configures it with vhost files and opens firewall on ports for
HTTP and HTTPS.

## Supported platforms
* Ubuntu

## Optional configuration variables
All variables under defaults are there to be overridden if needed.
* apache2_config_root - location of config files on the destination
* apache2_main_config - local apache2 config file to send to server.
* apache2_vhosts_dir - sites-enabled directory on target
* apache2_conf_dir - conf-enabled directory on target
* apache2_http_port: http port to use (opens this port on firewall)
* apache2_https_port: https port to use (opens this port on firewall)
* apache2_http_open: Is HTTP port open
* apache2_https_open: Is HTTPS port open
* apache2_http_proxy: Is HTTP port behind a proxy
* apache2_https_proxy: Is HTTPS port behind a proxy
* apache2_http_proxy_ip: IP of the HTTP proxy
* apache2_http_proxy_ip: IP of the HTTPs proxy

## mandatory variables:
* apache2_server_name: Server name
* apache2_local_config_dir: Where local config files are stored

## firewall handling
If apache2_http_open or apache2_https_open are True, and proxy is set to False, firewall will open HTTP and HTTPs ports respectfully.  
This can later be changed for example if the server is moved behind the proxy, by setting the apache2_http_proxy and/or apache2_https_proxy to True.
Appropriate firewall rules will be added and the other one will be removed.
