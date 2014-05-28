## ngx_http_mrb_hello_module

Embed the Power of mruby into NGINX

## INSTALL

### module and mruby

    $ git clone git://github.com/Lax/ngx_http_mrb_hello_module.git
    $ cd ngx_http_mrb_hello_module
    $ git submodule init
    $ git submodule update

    $ cd mruby && make && cd -

### Nginx

    $ git clone git://github.com/nginx/nginx.git
    $ cd nginx
    $ ./configure --add-module=/path/to/ngx_http_mrb_hello_module

## Config

    worker_processes 1;

    events {
            worker_connections 1024;
    }

    http {
            server {
                    listen 8080;
                    server_name localhost;

                    location / {
                            hello;
                    }
            }
    }


    curl http://127.0.0.1:8080