# Information Gathering (Reconnaisance)

- This is the first process in a penetration test - and exists for the purposes of knowing your target.
- Reconnaisance encompasses target discovery and insight on other information related to the target(s).
- From an external perspective - information gathering is basically OSINT i.e. gathering information that's already publicly available on the internet.
- Passive Recon is gathering information without engaging or probing the target in any way whereas Active Recon is obviously the opposite.

# Passive Reconnaisance 

-[ ] finding a target's IP address
```
host [URL]
```

Or use the ping command 
```
ping [URL]
```

*Discovering hidden directories*
Append the `/robots.txt` infront of a URL on the browser

*Identifying structure of the website's directories*
Append `/sitemap.xml` infornt of a URL on the browser

*Identifying web technologies running on a web server*
- Search and integrate either of the browser plugins `built-with` or `wappalyzer`.
- The alternative to these browser plugins is a linux tool called `whatweb`
```
whatweb [URL]
```

*Downloading a website for offline analysis*
Download the tool called `HTTrack` and give it the desired website's URL

*Discovering domain registrar and nameserver*
```
whois [URL]
```

*Discovering a website's SSL and TSL certificate information - and domain registrar*
Use https://www.netcraft.com/

*DNS reconnaisance*
```
dnsrecon -d [URL]
```

The same scan above can be done using https://dnsdumpster.com/

*Identifying presence of a web application firewall (WAF)
```
wafwoof [URL] -a
```

*Enumerating Subdomains*

```
sublist3r -d [URL] -e [browser_name]
```

*Web Application Enumeration with Google Dorks*
The search parameters below work on the google search engine. For more detailed attack parameters visit https://www.exploit-db.com/google-hacking-database/

- To get results specific to one target `site:[URL]` e.g `site:isc2.org`
- For results within a specific domain `site:[URL] inurl:[any_term]`
- To find all subdomains of a URL `site:*.[URL]` e.g `site:*.isc2.org`
- The parameter `intitle` will look for a term within the subdomain titles `site:*.[URL] intitle":[any_term]`
- To find a file within a webpage we use the `filetype` parameter `site:[URL] filetype:[file_type]
- If directories are listed on a website, use `intitle:index of`
- To potentially find leaked passwords or usernames `inurl:passwd.txt` or `intitle:passwd.txt`


*Finding older versions of a website*
- Visit https://archive.org/web/ for the WayBack Machine which takes instances of a website at different points in time.
- The google hacking search parameter `cache:[URL]` can also be utilized.

*Finding emails and usernames associated with an organization*
```
theHarvester -d [URL] -b [browser_names]
```

*Finding potential passwords for employee emails or phone numbers*
Search on https://haveibeenpwned.com/

# Active Reconnaisance


