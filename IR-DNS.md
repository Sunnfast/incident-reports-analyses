# Incident Report - DNS

A short incident report derived from the analysis of DNS and ICMP traffic in transit from a network protocol analyzer tool (tcpdump). This report was part of the coursework for the Google Cybersecurity Professional Certificate.

### Scenario
Several customers contacted your company to report that they were not able to access the company website www.yummyrecipesforme.com, and saw the error "destination port unreachable" after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you visit the website and you also receive the error "destination port unreachable." Next, you load your network analyzer tool, tcpdump, and load the webpage again. This time, you receive a lot of packets in your network analyzer. The analyzer shows that when you send UDP packets and receive an ICMP response returned to your host, the results contain an error message: "udp port 53 unreachable." 


## Summary

The UDP protocol reveals that the DNS server is down or unreachable. This was evinced by the logs from the network scan as the ICMP echo reply returned the error message, `udp port 53 unreachable` and port 53 is typically used for DNS services. Here, it is likely the DNS server is not responding. It coud also be an indicator of a malicious attack on the DNS server. Lastly, it could be due to a firewall misconfiguration.

## Analysis & Potential Causes

The incident occurred at 1:24 PM and several customers contacted our company to report that they were not able to access the company website www.yummyreciplesforme.com, and received the message "destination port unreachable."

The IT department first attempted to visit www.yummyrecipesforme.com and also encountered the error described (`destination port unreachable`). Then, the IT department used a network protocol analyzer (i.e. tcpdump) to review sent UDP packets and the ICMP response returned to our host. When the IT department examined the logs it appears that all of the logs had the same error that port 53 was unreachable. Investigation is still ongoing into this issue at this time. Next, the IT department will need to review the firewall settings to determine whether the traffic to port 53 is being blocked by the firewall, or whether the DNS server is down.

At this stage, it cannot be ruled out that this is an indication of a malicious attack on the DNS server to negatively impact the availability of our company’s website (e.g. DOS attack). However, there could also be a problem with the firewall configuration.
