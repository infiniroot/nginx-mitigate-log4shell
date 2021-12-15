# nginx-mitigate-log4shell
Mitigate log4shell (CVE-2021-44228 and CVE-2021-45046) vulnerability attacks using Nginx LUA script

Requires the Nginx lua module (https://www.nginx.com/resources/wiki/modules/lua/) to be enabled.

Use `include /path/to/mitigate-log4shell.conf;` in the `server {...}` context. Can be included in multiple server contexts.

Can also be placed in the `http {...}` context and is therefore automatically applied on every Nginx config.

More information in our blog article: https://www.infiniroot.com/blog/1155/using-nginx-lua-script-mitigate-log4shell-cve-2021-44228-vulnerability .
