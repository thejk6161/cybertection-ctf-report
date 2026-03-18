# cybertection-ctf-report
Burp Suite vulnerability assessment
Cybertection CTF - Vulnerability Report

Target: www.cybertectionctf.com  
Tool: Burp Suite Community Edition  
Date: March 17, 2026  
Tester: jasun khadka

Vulnerabilities Found

CRITICAL - Hardcoded Credentials
Username admin and password password found in plain text inside JavaScript file
Anyone can read the source code and log in without hacking
Fix: Move authentication to server side, never store credentials in frontend code

MEDIUM - Admin Path Enumeration
/admin path returns 404 confirming it exists on the server
Found using Burp Suite HTTP History
Fix: Return generic error pages that do not confirm restricted paths exist

LOW - Information Disclosure via robots.txt
/robots.txt is publicly accessible and returns HTTP 200
Reveals site structure to potential attackers
Fix: Restrict sensitive information in robots.txt

MEDIUM - Client Side Flag Validation
CTF flag checking happens in browser JavaScript not on the server
Can be read and manipulated by anyone
Fix: Move flag verification to server side API

Tool Used
Burp Suite Community Edition v2026.2.3

Method
Used Burp Suite to intercept HTTP traffic, analyze JavaScript source files and enumerate site paths.
