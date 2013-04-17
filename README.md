Selenium startup script
=======================

This is a simple startup script based on the jenkins startup script.

This startup script assumes you have selenium server 2.x installed in the dir `/var/log/selenium`
also assumes you have the pkg `daemon` installed and a java runtime installed (this was tested in ubuntu 10.04.4 with `openjdk-6-jdk`)

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


Install the selenium server 2.x in your home directory:

    sudo wget --no-check-certificate https://selenium.googlecode.com/files/selenium-server-standalone-2.32.0.jar -O /var/lib/selenium/selenium-server-standalone-2.32.0.jar


Create a symlink:

    cd /var/lib/selenium
    sudo ln -s selenium-server-standalone-2.32.0.jar selenium-server-standalone.jar
    

Create a default grid.yml configuration:

    sudo cp /local/repo/path/grid.yml /var/lib/selenium/
    

Copy the default file and the init.d file in the right locations:

    sudo cp /local/repo/path/etc/init.d/selenium /etc/init.d/
    sudo cp /local/repo/path/etc/default/selenium /etc/default/
   

Install the service startup:

    sudo update-rc.d selenium defaults
   

Start the selenium hub:

    sudo /etc/init.d/selenium start
    

Check the logs:

    sudo tail -f /var/log/selenium/selenium.log
    

The service configuration can be found in `/etc/default/selenium`





