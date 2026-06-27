# Web Infrastructure Design

This project covers the basics of web infrastructure design.

## Concepts

* Network basics
* Server
* Web server
* DNS
* Load balancer
* Monitoring
* Database
* SPOF
* High availability
* HTTPS
* Firewall

## Task 0: Simple Web Stack

This task designs a simple one-server web infrastructure for `www.foobar.com`.

The infrastructure contains:

* 1 domain name: `foobar.com`
* 1 DNS record: `www.foobar.com` pointing to `8.8.8.8`
* 1 server
* 1 web server: Nginx
* 1 application server
* 1 application code base
* 1 database: MySQL

## Main Issues

This infrastructure has several limitations:

* Single Point of Failure
* Downtime during maintenance or deployment
* Limited scalability when traffic increases
