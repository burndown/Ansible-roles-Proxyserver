# ansible-proxyserver
Ansible playbook for proxyserver

In this Playbook, 4 components are installed on VPS, they are: 
 - nginx, wroking as front-end proxy 
 - ssr and v2ray working as scientist tools
 - frp working as reverse proxy to help you expose a local server behind a NAT or firewall to the internet.
 
How it works:
SSR listen on 80 port, v2ray listen on 443 port, nginx listen on 2222, when SSR and v2ray receive normal request, it will work normally to help u bypass the GFW. when they receive http or https, the traffic will redirect to nginx, nginx works as web server and  display a static webpage. 

frp is used for nas and home router.

certbot is used to create SSL.
