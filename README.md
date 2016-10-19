This is a Vagrant box I built for my own needs. If it suits you, great!

Current version: 1.0.2

** DISCLAIMER: **

This box is provided "as-is", without any kind of warranties whatsoever. It should be used for development environments ONLY, and at your own risk.

Stack:

- Ubuntu Server 16.04.1 LTS (Xenial Xerus)
- SSH Server 7.2
- nginx 1.10.0
- PHP 7.0.8 (with PDO drivers for MySQL and SQL Server)
- MariaDB 10.0.27
- Redis 3.2.4
- Composer 1.2.1
- Node.js 6.9.0
- npm 3.10.9
- Gulp 1.2.2
- Ruby 2.3.1
- Sass 3.4.22
- redis-commander 0.4.2
- phpMyAdmin 4.5.4.1

User / Pass : vagrant / vagrant

Networks:

Adapter #1: NAT Network (DHCP)

phpMyAdmin: http://\<IP address / hostname\>/phpmyadmin

redis-commander: http://\<IP address / hostname\>:8081

On /home/vagrant/scripts I've placed 3 helper scripts one could use to help provision the machine.

Go to http://github.com/filipeaclima/devbox for an example Vagrantfile, feedback, requests, etc.
