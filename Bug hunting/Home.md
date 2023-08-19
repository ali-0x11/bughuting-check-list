
## search for acquisition and asn

- [ ] [crunch base](https://www.crunchbase.com/)
- [ ] [asn](https://bgp.he.net/)
- [ ] https://whois.arin.net
---------------------
## collecting subomains 

- [x] [[amass]]
- [x] [[subfinder]]
- [x] [[assetfinder]]
- [x] [[hook]]
- [x] [[oneforall]]
- [ ] [[metabigor]]
- [ ] reconftw
- [ ] [[puredns]]
- [ ] [[bbot]]
- [ ] [[dnsx]]
- [ ] chaos-downloader
- [ ] https://tools.whoisxmlapi.com/
- [ ] [[altdns]]
- [ ] [[Lilly]]
- [ ] [[gotator]]
- [ ] [[xurlfind3r]]
- [ ] [[shuffledns]]
- [ ] check for subdomains favicon
----------------------
## shodan

- [ ] ssl:"target[.]com"  200 http.title:"dashboard"  <!-- unauthenticated dashboard -->
- [ ] org:"target.com" x-jenkins 200 <!-- unauthenticated jenkins server -->
- [ ] ssl:"target.com" 200 proftpd port:21 <!-- proftpd port:21 org:"target.com" -->
- [ ] http.html:zabbix <!-- CVE-2022-24255 Main & Admin Portals: Authentication -->
- [ ] Bypass org:"target.com" http.title:"phpmyadmin" <!-- PhpMyAdmin -->
- [ ] ssl:"target.com" http.title:"BIG-IP" <!--F5 BIG-IP using CVE-2020-5902 -->
-------------------------------------
## Google dorks

- [ ] site:http://s3.amazonaws.com "target[.]com"
- [ ] site:http://blob.core.windows.net "target[.]com"
- [ ] site:http://googleapis.com "target[.]com"
- [ ] site:http://drive.google.com "target[.]com"
--------------------------------------------
## github dorks

- [ ] Org:"target" pwd/pass/passwd/password
- [ ] "target.atlassian" pwd/pass/passwd/password
- [ ] "target.okta" pwd/pass/passwd/password
- [ ] "Jira.target" pwd/pass/passwd/password
----------------------------
## javascript files recon

- [ ] Grep all urls from wayback or gau or katana.
	- [ ] Collect all js file ".js"
	- [ ] Filter js file:" httpx -content-type | grep 'application/javascript'"
	- [ ] Perform Nuclei scan "nuclei -t /root/nuclei-templates/exposures/"

- [ ] js Recon Tip:
	- [ ] Collect all endpoints from Js files & Create a wordlist from those.
	- [ ] Craft a POST request with any parameter.
	- [ ] Use that request to fuzz for sensitive directory.
-----------------
## Fuzzing

- [ ] [[ffuf]]
- [ ] [[fuzzuli]]
---------------------------
## screenshots

- [ ] [[gowitness]]
- [ ] [[aquatone]]
- [ ] [[Eyeballer]]
------------------------------
## port scanning

- [ ] [[naabu]]
-----------------------
## collecting URLS

- [ ] gau
- [ ] [[katana]]
- [ ] waybackurl
- [ ] [[gospider]]
- [ ] [[jsluice]]
- [ ] [[hakrawler]]
- [ ] [[xnLinkFinder]]
---------------------
## parameter fuzz
- [ ] [[arjun]]
- [ ] [[x8]]
- [ ] [[ParamSpider]]
-------------------------------------
## vulnerability scanners

- [ ] [[nuclei]]
- [ ] [[nrich]]
- [ ] [[wpscan]]
- [ ] [[subzy]]
- [ ] [[dalfox]]
- [ ] [[sqlifinder]]
- [ ] [[4-ZERO-3]]
- [ ] [[waybackSqliScanner]]
- [ ] [[sqlmap]]
- [ ] [[NucleiFuzzer]]
- [ ] [[OpenRedirector]]
- [ ] [[atscan]]
----------------------
## [[check lists]]

---------------------------------
## payloads

- [ ] [[XSS]]
- [ ] [[LFI]]
- [ ] [[open redirect]]
-------------
## wordlists

----------------
## one liner automation
## tips

- [ ] After collecting URLs, curl out the responses of the URLs and grep for the following URLs:

```
httpx -l <fileName> -rl 450 -t 150 -mr "drive.google|docs.google|/spreedsheets/d/|/docmuent/d/" 
```

OR

```
cat domains.txt | katana -silent | while read url; do cu=$(curl -s $url | grep -E '(drive. google | docs. google | spreadsheet\/d | document.\/d\/)'; echo -e "==> $url" "\n"" $cu"; done
```

- [ ] Using paramspider, gxss to detect Cross-site Scripting (XSS): 

```
cat params | qsreplace yogi | dalfox pipe --mining-dom --deep-domxss --mining-dict --remote-payloads=portswigger,payloadbox --remote-wordlists=burp,assetnote -o xssoutput.txt
```

```
cat alive.txt | waybackurls | gf xss | uro | httpx -silent | qsreplace '"><svg onload=confirm(1)>' | airixss -payload "confirm(1)" | tee xssBug3.txt
```

- [ ] xss oneliner with gospider 
```
gospider -S targets_urls.txt -c 10 -d 5 --blacklist ".(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|pdf|svg|txt)" --other-source | grep -e "code-200" | awk '{print $5}'| grep "=" | qsreplace -a | dalfox pipe -o result.txt
```
https://taksec.github.io/google-dorks-bug-bounty/
