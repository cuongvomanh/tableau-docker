# tableau

## Build image

```
docker build --compress -t pvtmert/tableau:2019.1.17.oracle ./
```

## Init password

```
docker exec -it tableau bash -- tabcmd initialuser --server 'localhost:8880' --username 'admin' --password 'Admin@123'
```

## Install mysql driver

```
sudo yum install gcc10-libstdc++-10.2.1-7.gf.el7.x86_64.rpm
sudo yum install mysql-community-client-plugins-8.0.22-1.el8.x86_64.rpm
sudo yum install mysql-connector-odbc-8.0.22-1.el7.x86_64.rpm
cat /etc/odbcinst.ini
```

## Install oracle driver

https://kb.tableau.com/articles/issue/error-clntsh-not-found-when-connecting-to-oracle

https://rpms.remirepo.net/enterprise/7/remi/x86_64/php55-php-pecl-oci8-2.0.11-1.el7.remi.x86_64.rpm

```
docker cp tableau-oracle-12.1.0.2.0-1.x86_64.rpm tableau:/
docker exec -it tableau bash
rpm -ivh tableau-oracle-12.1.0.2.0-1.x86_64.rpm
```

https://www.oracle.com/database/technologies/instant-client/linux-x86-64-downloads.html

```
yum install libaio
```
