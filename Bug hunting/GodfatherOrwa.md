
## Part 1

Talking about how i found bugs in small scope  And A Tip For Not Thinking Out of the Box, Thinking out of the House.

- start checking the domains and IP even it's out of scope. (basically to use the out of scope domains to check for bugs the in scope domains, take a look out of scope but dont test)

## Part 2

- github:
	- paste the domain without any addtions
	- search for: password, secret, pass, token, pwd, pw, passwd, private
	- use githubt filers: NOT <target>, language:<lang>, user:<username>
		- do not forget to check git.github.com

- shodan:
	- ssl:"<orgnisation name>" 200 (to get the live domains)
		- net : "<CIDR,CIDR,CIDR,>"
		- ssl: "Program Name"
		- Ssl.cert.subject.CN:"<Domain>" 200
		- http.title:"Grafana" 200
		- http.title:"Citrix Gateway" 200

- credentials:
	- admin:admin
	- admin:password
	- test:test
	- demo:demo
	- user:password

- ST jira:
	- test for SSRF
	- test for RCE (check this path: /secure/ContactAdministrator!defult.jspa)
	- check this path too it also lead to authnticatoin bypass (/servicedesk/customer/user/login)
