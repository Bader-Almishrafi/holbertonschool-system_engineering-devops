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


## Task 1: Distributed Web Infrastructure

This task designs a distributed web infrastructure for `www.foobar.com`.

The infrastructure contains:

* 1 load balancer server using HAProxy
* 2 web/application/database servers
* 2 Nginx web servers
* 2 application servers
* 2 sets of application files
* 2 MySQL databases configured as Primary-Replica

The load balancer distributes traffic between the two servers using the Round Robin algorithm.

This is an Active-Active setup because both servers are active and both receive traffic.

The database uses a Primary-Replica cluster. The Primary node handles write operations, while the Replica node copies data from the Primary and can be used for read operations.

Main issues:

* The load balancer is a Single Point of Failure
* The Primary database can be a Single Point of Failure for write operations
* No firewall
* No HTTPS
* No monitoring
