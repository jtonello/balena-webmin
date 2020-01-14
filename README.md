# balena-webmin
Multi-platform Webmin container for balenaCloud

### Introduction
Deploy Webmin in a container so you can view and manage a balenaCloud device via a browswer dashboard. By adding _bind9_ to the packages to be installed, Webmin can run and administer a DNS server. Webmin and Bind data persists in the following volumes:

* /etc/webin
* /var/webin 
* /etc/bind 
* /var/named 

Note that Bind is available in the Webmin dashboard, but is not initially running. On start (from the dashboard), port 53 is available for remote connections. Edit the _webmin/named.conf.options_ file to edit the trusted subnet for DNS querying.

The Webmin root password is set as a variable in the _.balena/balena.yml_ file. You should change it for production uses.

### Deploy
Clone this repository, change into the balenaWebmin directory and push to your application:
```
$ git clone git@github.com:jtonello/balenaWebmin.git
$ cd balena-webmin
$ balena push <appname>
```
