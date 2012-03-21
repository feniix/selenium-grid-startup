Selenium grid startup script
============================

This is a simple startup script based on the jenkins startup script.

the script assumes you have ant and ant-optional installed

also assumes you have the pkg daemon installed 

and the following already created in your linux box:

id: selenium

home: /var/lib/selenium-grid

shell: /bin/bash

selenium grid installation: /var/lib/selenium-grid/selenium-grid-1.0.8

log dir: /var/log/selenium owned by the selenium id

run: /var/run/selenium owned by the selenium id

