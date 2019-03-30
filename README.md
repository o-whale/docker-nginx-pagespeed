# Docker Nginx + PageSpeed + Let's Encrypt

This docker image based on Debian Stretch linux distribution.
Project goal is an easy to build docker image of latest Nginx web server with Google PageSpeed and Geo IP modules.

## PageSpeed

The [PageSpeed](https://developers.google.com/speed/pagespeed/) tools analyze and optimize your site following web best practices. If turned ON it exposes a PageSpeed admin status page at:

- ```http://localhost:8080/pagespeed_admin/```

## VTS

The [VTS](https://github.com/vozlt/nginx-module-vts) Nginx virtual host traffic status module. It exposes a status page at:

- ```http://localhost:8080/status/```

## More Headers

The [more_set_headers](https://github.com/openresty/headers-more-nginx-module)allows to set more HTTP response headers - useful in multi cluster environments.

## Substitutions Filter

The [subs_filter](https://github.com/yaoweibin/ngx_http_substitutions_filter_module) allows nginx to filter which can do both regular expression and fixed string substitutions on response bodies.

## Json access log

Container will produce web server access log through docker /stdout in json format for easy parsing via 3rd party containers like Fluentd.

## Main features

Include environment variables to turn ON | OFF Page Speed optimization features for:

- images
- javascripts
- style sheets
- cache engine for cluster environments: files, memcached or redis

as well as:

- vhosts stats page
- default host with health check

Nginx is configured by default for high performance, multi cluster production environment, but can be easily adjusted with environment variables. Check [.env-example](https://github.com/o-whale/docker-nginx-pagespeed/blob/master/.env-example)
