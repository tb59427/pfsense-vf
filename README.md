# pfsense-vf
login to captive portal using vereinsflieger

patchfile wil eventually contain all patches to php files necessary to interface vereinsflieger with pfsense

currently it does not contain changes to captive portal configuration

pfSense files changed

/etc/inc/VereinsfliegerRestInterface.php
(REST wrapper to talk to Vereinsflieger) is just being added to /etc/inc

/usr/local/captiveportal/index.php
contains changes needed to authenticate against vereinsflieger

/usr/local/www/services_captiveportal.php
contains changes to allow configuration of vereinsflieger authentication
