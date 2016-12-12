# pfsense-vf
login to captive portal using vereinsflieger

12.12.16 - first full release (use with a lot of caution)

USE AT YOUR OWN RISK

What works/what doesn't
- login using vereinsflieger in an appropriate configured captive portal works
- use of vereinsflieger CID works
- UNTESTED: multiple zones with this login switch on/off
- configuration does still look a bit clumsy

The following pfSense files are changed by this patch (YOUR SHOULD BACK THESE UP BEFORE YOU INSTALL!!! - e.g. by compying them to ...orig)
/etc/inc/VereinsfliegerRestInterface.php
(REST wrapper to talk to Vereinsflieger) is just being added to /etc/inc

/usr/local/captiveportal/index.php
contains changes needed to authenticate against vereinsflieger - DO BACK THIS ONE UP

/usr/local/www/services_captiveportal.php
contains changes to allow configuration of vereinsflieger authentication - DO BACK THIS ONE UP

Mini-How-To:
1. install "system patches" packages
2. go to System->Patches
3. "Add New Patch"
4. Pick a suitable description, like: Vereinsflieger Login
5. URL/Commit ID is the raw URL of patchfile (https://raw.githubusercontent.com/tb59427/pfsense-vf/master/patchfile)
6. Set Path Strip Count to 0
7. Set Base Directory to /
8. Check "ignore whitespace..."
9. Uncheck "auto apply" (unless you really want to :-)
10. Save

Now (really!) back up the above files. 
Hit the Test Button. It should tell you, that this patch can be applied but can' be reverted (normal)
Apply

There is an additional section now in the captive portal config (Services->Captive Portal) under Authentication. it allows you to 
switch on vereinsflieger authentication. Currently only works if local authentication is enabled.
Add your vereinsflieger CID or put a 0 there in case anyone with a vereinsflieger login is welcome in your WIFI
