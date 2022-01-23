# nginx.conf 
The default `nginx.conf` have been modified to add some security headers.
It is also modified to read config files from `/etc/nginx/conf.d` directory with `*.conf` file extension. 
If config needs to be disabled just change the extension other than `.conf` Ex. `example.conf.disabled`


## HTTP requests are 301 redirected to HTTPS for both  api.xyz.us and app.xyz.us

# api.xyz.us.conf
Servers the api/backend 
Whenever https://api.mightybyte.us gets request, it forwards it to backend server along with host and remote address headers.

# app.xyz.us.conf
Servers the static frontend files 
Whenever a request comes on https://app.mightybyte.us it servers the requested files from `/var/www/app` directory 

Caching of static files has not been applied. It can be applied 