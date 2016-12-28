This is a Vagrant box I built for my own needs. If it suits you, great!

Current version: 1.1.5

** DISCLAIMER: **

This box is provided "as-is", without any kind of warranties whatsoever. It should be used for development environments ONLY, and at your own risk.

Stack:

- Ubuntu Server 16.10 (Yakkety Yak)
- SSH Server 7.3
- nginx 1.10.1
- PHP 7.0.8 (with PDO drivers for MySQL and SQL Server)
- MariaDB 10.0.28
- Redis 3.2.6
- Composer 1.3.0
- Node.js 7.3.0
- npm 4.1.1
- Gulp 1.2.2
- Ruby 2.3.1
- Sass 3.4.23
- node-sass 4.1.1
- redis-commander 0.4.2
- phpMyAdmin 4.6.4

User / Pass : vagrant / vagrant

Networks:

Adapter #1: NAT Network (DHCP)

phpMyAdmin: http://\<IP address / hostname\>/phpmyadmin

redis-commander: http://\<IP address / hostname\>:8081

On /home/vagrant/scripts I've placed 3 helper scripts one could use to help provision the machine.

Go to http://github.com/filipeaclima/devbox for an example Vagrantfile, feedback, requests, etc.
