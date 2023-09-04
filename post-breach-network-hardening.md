# Analysis - Post-Breach Network Hardening

A set of recommendations for security hardening practices to be implemented in a social media organization in response to recent data breach. This analysis was part of the coursework for the Google Cybersecurity Professional Certificate.

### Scenario [excerpt]

You are a security analyst working for a social media organization. The organization recently experienced a major data breach [...] Your organization wants to implement strong network hardening practices that can be performed consistently to prevent attacks and breaches in the future. 

## Identification
There are four major vulnerabilities with ther organization's systems:
1. The organization’s employees' share passwords.
2. The admin password for the database is set to the default.
3. The firewalls do not have rules in place to filter traffic coming in and out of the network.
4. Multifactor authentication (MFA) is not used.

## Recommendations

The implementation of a password policies would prohibit conduct like employees sharing passwords with each other at the organization. Additionally, using The National Institute of Standards (NIST) latest recommendation for password policies would involve using methods to salt and hash the passwords as opposed to requiring overly complex passwords. Since overly complex passwords would not be necessary employees would lose the incentive to share passwords in violation of any new policies.

The next recommendation would be implementing multifactor authentication. Currently, the organization is using single factor authentication which is vulnerable to brute force attacks. Multifactor authentication is security control that requires a user to verify their identity in two or more ways (something you know, something you have, something you are, etc) in order to access a system or a network. As a result, this measure can also protect against brute force attacks. This measure can also be maintained with a minimal burden on the cybersecurity team once implemented.

Firewall maintenance would be the third recommendation. The organization already has firewalls in place, however, they currently do not have rules in place to filter incoming or outgoing network traffic. Firewall maintenance involves reviewing and updating the firewall security configurations on a regular basis to anticipate and mitigate potential threats. Practically, firewall rules can be updated in response to an event that allows suspicious network traffic into the network. This security measure is particularly effective to prevent various forms of distributed denial of service (DDoS) attacks.

The final recommendation is the use of port filtering in the pre-existing firewalls in the organization. Port filtering is a function of a firewall that blocks or allows  certain port numbers (depending on the configuration) to limit any undesired communication. This is used to control network traffic and ultimately can prevent a potential attacker from entering into the network.
