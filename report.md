# Incident Report

## Summary

The UDP protocol reveals that port 53 is unreachable when attempting to access yummrecipesforme.com. The port noted in the error message is typically used for DNS services. This may indicate a problem with the DNS server or firewall configuration. It coud also be an indicator of a malicious attack on the DNS server.

## Analysis & Potential Causes

The incident occurred at 1:24 PM and several customers contacted our company to report that they were not able to access the company website www.yummyreciplesforme.com, and saw "destination port unreachable."

The IT department first attempted to visit www.yummyrecipesforme.com and also encountered the error described ("destination port unreachable"). Next, the IT department used a network protocol analyzer (i.e. tcpdump) to review sent UDP packets and the ICMP response returned to our host. 

When the IT department examined the logs it appears that all of the logs had the same error that port 53 was unreachable even when requests were made from IT devices on the internal network. At this stage, it cannot be ruled out that this is an indication of a malicious attack on the DNS server to negatively impact the availability of our company’s website (e.g. DOS attack). However, there could also be a problem with the DNS server or firewall configuration.
