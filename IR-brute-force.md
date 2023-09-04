# Incident Report - Brute Force Attack

A short incident report derived from the analysis of data from a network protocol analyzer (tcpdump) in response to suspicious website behavior. This report was part of the coursework for the Google Cybersecurity Professional Certificate.

### Scenario [excerpt]

You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A disgruntled baker has decided to publish the website’s best-selling recipes for the public to access for free. 

The baker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After running the downloaded file, the customers are redirected to a fake version of the website where the seller’s recipes are now available for free.

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to update their browsers. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly. 

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.

## Identification
The network protocol involved in this incident was the Hypertext transfer protocol (HTTP) which occurs at the application layer. The DNS & HTTP traffic log file indicates that the user is prompted to download a file that is actually malicious in nature. Once the file is downloaded and is executed the logs demonstrate that the user’s browser sends a new request to a DNS server to resolve the IP address for a different URL entirely (greatrecipesforme.com). The DNS server resolves the URL and the users are redirected to the other website via HTTP.

## Documentation of the Incident

Multiple customers emailed yummyrecipesforme’s helpdesk complaining that the company’s website had prompted them to download a file to update their web browser. The customers had also noted that after running the downloaded “update” file that the address of the website changed as well.

The website owner attempted to log in to the administrative panel but was unable to and reached out to the website hosting provider. The cybersecurity analyst first created a sandbox to observe the dubious website behavior. The analyst used tcpdump, and then entered in the URL for yummyrecipesforme.com. When the website loaded, a prompt appeared to download an executable file to “update” the browser. To emulate customer behavior, they downloaded the file and allowed it to run. After execution of the file, they observed that the browser redirects to a different URL (greatrecipesforme.com). This website imitates the original website (yummyrecipesforme), but the recipes that the company sells are freely accessible on the website and no longer behind a paywall.

The cybersecurity analyst reviewed the tcpdump log and observed that the browser initially requested the IP address for the yummyrecipesforme.com website, which is typical and expected behavior. After the connection with the website was established over the HTTP protocol, at that point the analyst had downloaded and executed the “update” file. The corresponding logs then indicate that there was a change in network traffic and the browser requested a different IP address for “greatrecipesforme.com” URL. The network traffic rerouted to the new IP address greatrecipesforme.com instead of staying on yummyrecipesforme.com.

The senior cybersecurity professional analyzed the source code for the website and the downloaded website and noted that an attacker had manipulated the website to add code. The new code prompted website visitors to download a malicious file masquerading as a browser update. Given that the website owner has been locked out of their administrator account, the cybersecurity team postulates that the attacker used a brute force attack to gain access to the admin account and changed the password.


## Mitigation Strategies

The brute force attack was likely successful because a single factor authentication system (SFA) was in place. Upgrading to a multi-factor authentication system (MFA) would require users to provide more forms of authentication in addition to the password. For example, it could be a one time password generated from the user’s phone’s authenticator application. Even if a malicious actor were able to determine the password via a brute force attack they will not gain access to the system as they would be missing the remaining required forms of authentication.

Since the malicious actor was able to gain access by guessing several known default passwords for the administrative account, implementing a password policy would be prudent. Specifically, the admin account should need to conform to minimum password complexity requirements and be required to be changed after a certain period of time. 

