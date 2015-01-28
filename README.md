# notes-on-servers
General notes and tutorials about server set-ups.

#Digital Ocean

## Ubuntu

[MySQL tutorial](https://help.ubuntu.com/lts/serverguide/mysql.html)

[PostgreSQL tutorial](https://help.ubuntu.com/community/PostgreSQL)
```
sudo apt-get install postgresql postgresql-contrib
sudo apt-get install pgadmin3
```
Setting password for postgresql
```
sudo -u postgres psql postgres
\password postgres
```
```
server {
    listen       80;
    server_name  anigrams.colelawr.com;

    access_log /var/www/anigrams/logs/access.log;
    error_log /var/www/anigrams/logs/error.log;
    root /var/www/anigrams/wordpress;
    location ~ \.php$ {
        include /etc/nginx/fastcgi_params;
        fastcgi_pass 127.0.0.1:9000;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME /var/www/anigrams/wordpress$fastcgi_script_name;
    }
}
```
