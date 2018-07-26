# Simple MySQL High Availability demo using Docker and MySQL 5.7

## requirements:
- Docker
- docker-compose

## Setup

`$ docker-compose up`

It is probably necessary to allow remote connections so you can work from your host machine. You will have to do this for both hosts:

`$ docker exec -it db<1|2> bash`

In docker container:

`$ echo "GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'' IDENTIFIED BY 'password'" | mysql -uroot -ppassword`

After doing this in both containers just logout.

Verify from host machine:

`$ mysql -uroot -ppassword -h127.0.0.1 -P3307`
`$ mysql -uroot -ppassword -h127.0.0.1 -P3308`

After that you can follow this guide:

https://www.linode.com/docs/databases/mysql/configure-master-master-mysql-database-replication/#create-replication-users
