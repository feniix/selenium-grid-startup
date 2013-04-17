Selenium grid startup script
============================

This is a simple startup script based on the jenkins startup script.

the script assumes you have ant and ant-optional installed

also assumes you have the pkg daemon installed 

and the following already created in your linux box:

id: selenium
home: /var/lib/selenium
shell: /bin/bash
selenium installation directory: /var/lib/selenium

    sudo groupadd -r selenium
    sudo useradd -r -d /var/lib/selenium -s /bin/bash -m -g selenium -G selenium selenium

log dir: /var/log/selenium owned by the selenium id

    sudo mkdir /var/log/selenium
    sudo chown selenium.selenium /var/log/selenium


