# Name Resolution

## Why do we need DNS?

- Human brain is not good at remembering numbers
- So a system called DNS is developed to assign those IP addresses to memorable domain names

### Domain Name System (DNS)

"A global and highly distributed network service that resolves strings of letters into IP addresses for you."

### Domain Name

"The term we use for something that can be resolved by DNS."

## The Many Steps of Name Resolution

There are five primary types of DNS servers;

- Caching name servers

- Recursive name servers

- Root name servers (13 root servers all over world)

- TLD name servers

- Authoritative name servers

### Caching and Recursive name servers

Purpose is to store known domain name lookups for a certain amount of time.

### Recursive name servers

- Perform full DNS resolution requests

- Time to live (TTL)

  > A value, in seconds, that can be configured by the owner of a domain name for how long a name server is allowed to cache an entry before it should discard it and perform a full resolution again

### A Typical DNS Query

![A DNS query: Step 1](./images/dns_resolution.png) 

![Step 2](./images/dns_resolution_2.png)

![Step 3](./images/dns_resolution_3.png)

![Step 4](./images/dns_resolution_4.png)

![Step 5](./images/dns_resolution_5.png)

### Anycast

"A technique that's used to route traffic to different destinations depending on factors like location, congestion, or link health."

## DNS and UDP

- DNS, an application layer service, uses UDP

- A full DNS lookup with TCP in use, will use 44 total packets

  ![A DNS resolution with TCP](./images/dns_resolution_tcp.png) 

- A full DNS lookup with UDP on the other hand require only 8 packets

- Error recovery is done by asking again in the UDP as no error check is present

![A DNS Lookup with UDP](./images/dns_resolution_udp.png) 

# Name Resolution is Practice

## Resource Record Types

### A record

"An **A record** is used to point a certain domain name at a certain IPv4 IP address."

- A single A record is configured for single domain

- But a single domain name can have multiple A records, this allows for a technique known as **DNS round-robin** to be used to balance traffic across multiple IPs
  
  > Round-robin is a concept that involves iterating over a list of items one by one in an orderly fashion. The hope is that this ensures a fairly equal balance of each entry on the list that's selected.

### AAAA - Quad A

"Quad A record is used to point a certain domain name at a certain IPv6 IP address."

### CNAME

"A CNAME record is used to redirect traffic from one domain name to another."

### MX record - mail exchange

"This resource record is used in order to deliver e-mail to the correct server."

### SRV record - service record

"It's used to define the location of various specific services."

- MX record is only used for e-mails, SRC is used for every other service
  
  + I.e. caldav (calendar and scheduling service)

### TXT record - text 

- Used to communicate configuration preferences of a domain

## Anatomy of a Domain Name

### Top level domain (TLD)

The last part of a domain name. E.g. **.com, .net etc.**

- TLDs are handled by non-profit **The Internet Corporation for Assigned Names and Number (ICANN)** 

- **ICANN** is a sister organization to **IANA**, together both help define and control the global IP spaces and DNS system

### Domains

"Used to demarcate where control moves from a TLD name server to an authoritative name server."

### Subdomain

"The **www** portion of a domain."

### Full qualified domain name (FQDN)

When you combine all of these parts together, you have what's known as this.

- A DNS can technically support up to **127 level** of domain in total for a single fully qualified domain name

- Some other restrictions are, each individual section can only be **63 characters** and a **complete FQDN** is limited to **255 characters**
