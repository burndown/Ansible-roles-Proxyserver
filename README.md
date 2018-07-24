# ansible-proxyserver
Ansible playbook for proxyserver

In this Playbook, 4 components are installed on Ubuntu, they are: 
 - nginx, wroking as front-end proxy 
 - ssr and v2ray working as scientist tools
 - frp working as reverse proxy to help you expose a local server behind a NAT or firewall to the internet.
 
How it works:

SSR listen on 80 port, nginx listen on 2222 and 443, when SSR receive normal request, it will work normally to help u bypass the GFW. when Nginx receive request with header - "www.chinadream", it will redirect the request to v2ray, who will process it and help u bypass the firewall, when ssr receive http request and nginx receive https without correct header(chinadream), the traffic will fall back to nginx, when nginx works as web server and  display a static webpage. 


frp is used for nas and home router.

certbot is used to create SSL.

How to use it:

Ansible version >= 2.4

before use the playbook, remember replace proxy domain name in var, which locate in roles/nginx/default/main.yml to your own domain name
