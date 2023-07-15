# nginx-rewrite-rules

Simple example of rewrite rules for Nginx



## Usage

```bash
sudo vim /etc/nginx/conf.d/example.com.conf
```
create a server block
```bash
server {
    listen 80;
    server_name localhost;
    root /var/www/example.com;

    location / {
        rewrite ^/old-url$ /new-url permanent;
    rewrite ^/old-file.php$ /new-file.php permanent;
    }
}
```
make a directory for this virtual host
```bash
sudo mkdir /var/www/example.com
```
create HTML file
```bash
sudo vim /var/www/example.com/index.html
```
HTML file contents
```bash
<!DOCTYPE html>
<html>
<head>
    <title>Example.com</title>
</head>
<body>
    <h1>Welcome to Example.com!</h1>
</body>
</html>
```
to test server
curl IP(or localhost)
### Now if you just test the server by curl -I http://example.com/old-url you just redirect to http://example.com/new-url

