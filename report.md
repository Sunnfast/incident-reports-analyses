# Incident Report

## Summary

The UDP protocol reveals that the DNS server is down or unreachable. This was evinced by the logs from the network scan as the ICMP echo reply reutnred the error message, "udp port 53 unreacahble" and port 53 is typically used for DNS services. Here, it is likely the DNS server is not responding. It coud also be an indicator of a malicious attack on the DNS server. Lastly, it could be due to a firewall misconfiguration.

## Analysis & Potential Causes

The incident occurred at 1:24 PM and several customers contacted our company to report that they were not able to access the company website www.yummyreciplesforme.com, and received the message "destination port unreachable."

The IT department first attempted to visit www.yummyrecipesforme.com and also encountered the error described ("destination port unreachable"). Then, the IT department used a network protocol analyzer (i.e. tcpdump) to review sent UDP packets and the ICMP response returned to our host. When the IT department examined the logs it appears that all of the logs had the same error that port 53 was unreachable. Investigation is still ongoing into this issue at this time. Next, the IT department will need to review the firewall settings to determine whether the traffic to port 53 is being blocked by the firewall, or wehther the DNS server is down.

At this stage, it cannot be ruled out that this is an indication of a malicious attack on the DNS server to negatively impact the availability of our company’s website (e.g. DOS attack). However, there could also be a problem with the firewall configuration.
